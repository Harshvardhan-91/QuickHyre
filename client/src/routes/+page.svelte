<script lang="ts">
  import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card';
  import { Badge } from '$lib/components/ui/badge';
  import { Button } from '$lib/components/ui/button';
  import { Table, TableBody, TableCell, TableHead, TableHeader, TableRow } from '$lib/components/ui/table';
  import { ArrowDown, ArrowUp, Search } from 'lucide-svelte';

  // Data for stats cards
  const stats = [
    { title: 'Open Positions', value: 24, change: '+2 this week', changeColor: 'text-green-500' },
    { title: 'Active Candidates', value: 254, change: '+18 this week', changeColor: 'text-green-500' },
    { title: 'New Applications', value: 42, change: '+8 today', changeColor: 'text-green-500' },
    { title: 'Conversion Rate', value: '24%', change: '-2% this month', changeColor: 'text-destructive' },
  ];

  // Data for job postings
  const jobs = [
    {
      title: 'Senior Frontend Developer',
      location: 'Remote',
      teamSize: '10-15 people',
      posted: '2 weeks ago',
      applications: 24,
      skills: ['React', 'TypeScript', 'Node.js'],
      status: 'Active',
    },
    {
      title: 'UX Designer',
      location: 'New York, NY',
      teamSize: '5-8 people',
      posted: '1 week ago',
      applications: 18,
      skills: ['Figma', 'Adobe XD', 'Sketch'],
      status: 'Active',
    },
    {
      title: 'Product Manager',
      location: 'San Francisco, CA',
      teamSize: '8-12 people',
      posted: '3 days ago',
      applications: 12,
      skills: ['PostgreSQL'],
      status: 'Active',
    },
  ];

  // Data for hiring pipeline
  const pipeline = [
    { stage: 'Applied', count: 120 },
    { stage: 'Screening', count: 82 },
    { stage: 'Interview', count: 42 },
    { stage: 'Assessment', count: 28 },
    { stage: 'Offer', count: 14 },
    { stage: 'Hired', count: 8 },
  ];

  // Data for recent applications
  const applications = [
    {
      candidate: 'Alex Johnson',
      email: 'alexj@example.com',
      position: 'Senior Frontend Developer',
      experience: '8 years exp',
      skills: ['React', 'TypeScript'],
      newSkills: 1,
      match: '92%',
      status: 'New',
    },
    {
      candidate: 'Morgan Smith',
      email: 'morgan@example.com',
      position: 'UX Designer',
      experience: '5 years exp',
      skills: ['Figma', 'UI/UX'],
      newSkills: 1,
      match: '88%',
      status: 'In Review',
    },
  ];
</script>

<div class="space-y-6">
  <!-- Welcome Message -->
  <h3 class="text-lg text-muted-foreground">Welcome back! Here's what's happening with your recruitment activities.</h3>

  <!-- Stats Cards -->
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
    {#each stats as stat}
      <Card>
        <CardHeader>
          <CardTitle class="text-sm font-medium text-muted-foreground">{stat.title}</CardTitle>
        </CardHeader>
        <CardContent>
          <p class="text-2xl font-bold text-foreground">{stat.value}</p>
          <p class={`text-sm ${stat.changeColor}`}>{stat.change}</p>
        </CardContent>
      </Card>
    {/each}
  </div>

  <!-- Job Postings and Hiring Pipeline -->
  <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
    <!-- Job Postings -->
    <Card>
      <CardHeader class="flex items-center justify-between">
        <CardTitle class="text-foreground">Job Postings</CardTitle>
        <Button>+ New Job</Button>
      </CardHeader>
      <CardContent>
        {#each jobs as job}
          <div class="border-b border-border py-4 last:border-b-0">
            <div class="flex items-center justify-between">
              <div>
                <h4 class="text-lg font-semibold text-foreground">{job.title}</h4>
                <p class="text-sm text-muted-foreground">{job.location}</p>
                <p class="text-sm text-muted-foreground">{job.teamSize}</p>
                <p class="text-sm text-muted-foreground">{job.posted}</p>
                <div class="flex space-x-2 mt-2">
                  {#each job.skills as skill}
                    <Badge variant="secondary">{skill}</Badge>
                  {/each}
                </div>
              </div>
              <div class="text-right">
                <Badge variant="success">{job.status}</Badge>
                <p class="text-sm text-muted-foreground mt-2">{job.applications} Applications</p>
                <div class="flex space-x-2 mt-2">
                  <Button variant="outline" size="sm">Edit</Button>
                  <Button variant="outline" size="sm">View</Button>
                </div>
              </div>
            </div>
          </div>
        {/each}
      </CardContent>
    </Card>

    <!-- Hiring Pipeline -->
    <Card>
      <CardHeader>
        <CardTitle class="text-foreground">Hiring Pipeline</CardTitle>
      </CardHeader>
      <CardContent>
        <div class="flex items-end space-x-4">
          {#each pipeline as stage}
            <div class="flex-1 text-center">
              <div
                class="bg-primary rounded-t-lg"
                style={`height: ${stage.count * 1.5}px; min-height: 20px;`}
              ></div>
              <p class="text-sm text-muted-foreground mt-2">{stage.stage}</p>
              <p class="text-lg font-semibold text-foreground">{stage.count}</p>
            </div>
          {/each}
        </div>
      </CardContent>
    </Card>
  </div>

  <!-- Additional Stats -->
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
    <Card>
      <CardHeader>
        <CardTitle class="text-sm font-medium text-muted-foreground">Average Time to Hire</CardTitle>
      </CardHeader>
      <CardContent>
        <p class="text-2xl font-bold text-foreground">32 days</p>
        <p class="text-sm text-green-500 flex items-center">
          <ArrowDown class="w-4 h-4 mr-1" /> 3 days from last month
        </p>
      </CardContent>
    </Card>
    <Card>
      <CardHeader>
        <CardTitle class="text-sm font-medium text-muted-foreground">Cost per Hire</CardTitle>
      </CardHeader>
      <CardContent>
        <p class="text-2xl font-bold text-foreground">$2,140</p>
        <p class="text-sm text-destructive flex items-center">
          <ArrowUp class="w-4 h-4 mr-1" /> $120 from last month
        </p>
      </CardContent>
    </Card>
    <Card>
      <CardHeader>
        <CardTitle class="text-sm font-medium text-muted-foreground">Quality of Hire</CardTitle>
      </CardHeader>
      <CardContent>
        <p class="text-2xl font-bold text-foreground">85%</p>
        <p class="text-sm text-green-500 flex items-center">
          <ArrowUp class="w-4 h-4 mr-1" /> 5% from last month
        </p>
      </CardContent>
    </Card>
    <Card>
      <CardHeader>
        <CardTitle class="text-sm font-medium text-muted-foreground">Recruiter Efficiency</CardTitle>
      </CardHeader>
      <CardContent>
        <p class="text-2xl font-bold text-foreground">42 apps/week</p>
        <p class="text-sm text-green-500 flex items-center">
          <ArrowUp class="w-4 h-4 mr-1" /> 4 from last month
        </p>
      </CardContent>
    </Card>
  </div>

  <!-- Recent Applications -->
  <Card>
    <CardHeader class="flex items-center justify-between">
      <CardTitle class="text-foreground">Recent Applications</CardTitle>
      <div class="relative">
        <Search class="absolute left-3 top-1/2 transform -translate-y-1/2 text-muted-foreground" size={20} />
        <input
          type="text"
          placeholder="Filter"
          class="pl-10 pr-4 py-2 rounded-lg bg-muted text-foreground focus:outline-none focus:ring-2 focus:ring-ring"
        />
      </div>
    </CardHeader>
    <CardContent>
      <Table>
        <TableHeader>
          <TableRow>
            <TableHead>Candidate</TableHead>
            <TableHead>Position</TableHead>
            <TableHead>Skills</TableHead>
            <TableHead>Match</TableHead>
            <TableHead>Status</TableHead>
            <TableHead>Actions</TableHead>
          </TableRow>
        </TableHeader>
        <TableBody>
          {#each applications as app}
            <TableRow>
              <TableCell>
                <div>
                  <p class="font-medium text-foreground">{app.candidate}</p>
                  <p class="text-sm text-muted-foreground">{app.email}</p>
                  <p class="text-sm text-muted-foreground">{app.experience}</p>
                </div>
              </TableCell>
              <TableCell>{app.position}</TableCell>
              <TableCell>
                <div class="flex space-x-2">
                  {#each app.skills as skill}
                    <Badge variant="secondary">{skill}</Badge>
                  {/each}
                  {#if app.newSkills > 0}
                    <Badge variant="outline">+{app.newSkills}</Badge>
                  {/if}
                </div>
              </TableCell>
              <TableCell>
                <Badge variant="outline">{app.match}</Badge>
              </TableCell>
              <TableCell>
                <Badge variant={app.status === 'New' ? 'default' : 'secondary'}>{app.status}</Badge>
              </TableCell>
              <TableCell>
                <Button variant="outline" size="sm">View</Button>
              </TableCell>
            </TableRow>
          {/each}
        </TableBody>
      </Table>
    </CardContent>
  </Card>
</div>