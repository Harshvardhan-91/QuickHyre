<div class="min-h-screen bg-gray-50 flex">
  <!-- Sidebar -->
  <aside class="w-64 bg-white border-r border-gray-200 flex flex-col p-6">
    <h1 class="text-2xl font-bold text-blue-700 mb-8">RecruitAI</h1>
    <nav class="flex-1">
      <ul class="space-y-4">
        <li><a href="#" class="flex items-center text-gray-700 hover:text-blue-600 font-medium"><span class="material-icons mr-2">dashboard</span>Dashboard</a></li>
        <li><a href="#" class="flex items-center text-gray-700 hover:text-blue-600 font-medium"><span class="material-icons mr-2">work</span>Jobs</a></li>
        <li><a href="#" class="flex items-center text-gray-700 hover:text-blue-600 font-medium"><span class="material-icons mr-2">people</span>Candidates</a></li>
        <li><a href="#" class="flex items-center text-gray-700 hover:text-blue-600 font-medium"><span class="material-icons mr-2">assignment</span>Applications</a></li>
        <li><a href="#" class="flex items-center text-gray-700 hover:text-blue-600 font-medium"><span class="material-icons mr-2">assessment</span>Assessments</a></li>
      </ul>
    </nav>
    <div class="mt-10">
      <h2 class="text-lg font-semibold text-gray-600 mb-2">Team</h2>
      <a href="#" class="flex items-center text-gray-700 hover:text-blue-600 font-medium"><span class="material-icons mr-2">group</span>Team Members</a>
    </div>
  </aside>

  <!-- Main Content -->
  <main class="flex-1 p-10">
    <header class="flex items-center justify-between mb-8">
      <h2 class="text-3xl font-bold text-gray-800">Recruiter Dashboard</h2>
      <div class="flex items-center space-x-4">
        <button class="bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700 transition">+ New Job</button>
        <span class="material-icons text-gray-500">notifications</span>
        <span class="material-icons text-gray-500">mail</span>
      </div>
    </header>
    <section>
      <h3 class="text-xl font-semibold mb-6">Welcome back! Here's what's happening with your recruitment activities.</h3>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-10">
        <div class="bg-white rounded-lg shadow p-6">
          <div class="text-gray-500 mb-2">Open Positions</div>
          <div class="text-3xl font-bold text-blue-700">24</div>
          <div class="text-green-500 mt-1">+2 this week</div>
        </div>
        <div class="bg-white rounded-lg shadow p-6">
          <div class="text-gray-500 mb-2">Active Candidates</div>
          <div class="text-3xl font-bold text-blue-700">254</div>
          <div class="text-green-500 mt-1">+18 this week</div>
        </div>
        <div class="bg-white rounded-lg shadow p-6">
          <div class="text-gray-500 mb-2">New Applications</div>
          <div class="text-3xl font-bold text-blue-700">42</div>
          <div class="text-green-500 mt-1">+8 today</div>
        </div>
        <div class="bg-white rounded-lg shadow p-6">
          <div class="text-gray-500 mb-2">Conversion Rate</div>
          <div class="text-3xl font-bold text-blue-700">24%</div>
          <div class="text-red-500 mt-1">-2% this month</div>
        </div>
      </div>
      <div class="bg-white rounded-lg shadow p-6">
        <h4 class="text-lg font-semibold mb-4">Job Postings</h4>
        <ul class="divide-y divide-gray-100">
          <li class="py-3 flex items-center justify-between">
            <span class="font-medium text-gray-700">Senior Frontend Developer</span>
            <span class="bg-green-100 text-green-700 px-3 py-1 rounded-full text-xs">Active</span>
          </li>
          <li class="py-3 flex items-center justify-between">
            <span class="font-medium text-gray-700">Backend Engineer</span>
            <span class="bg-yellow-100 text-yellow-700 px-3 py-1 rounded-full text-xs">Interviewing</span>
          </li>
          <li class="py-3 flex items-center justify-between">
            <span class="font-medium text-gray-700">UI/UX Designer</span>
            <span class="bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs">Closed</span>
          </li>
        </ul>
      </div>
    </section>
  </main>
</div>

<!-- Google Material Icons CDN for icons (optional, or use lucide/heroicons if preferred) -->
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet" />
