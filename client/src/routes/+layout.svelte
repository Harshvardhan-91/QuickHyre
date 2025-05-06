<script lang="ts">
  import { Button } from '$lib/components/ui/button';
  import { Bell, Mail, Search, User } from 'lucide-svelte';
</script>

<div class="flex h-screen bg-background">
  <!-- Sidebar -->
  <aside class="w-64 bg-sidebar-background shadow-md flex flex-col border-r border-sidebar-border">
    <!-- Logo -->
    <div class="p-4">
      <h1 class="text-2xl font-bold text-sidebar-primary">RecruitAI</h1>
    </div>

    <!-- Search Bar -->
    <div class="px-4 py-2">
      <div class="relative">
        <Search class="absolute left-3 top-1/2 transform -translate-y-1/2 text-muted-foreground" size={20} />
        <input
          type="text"
          placeholder="Search..."
          class="w-full pl-10 pr-4 py-2 rounded-lg bg-muted text-foreground focus:outline-none focus:ring-2 focus:ring-sidebar-ring"
        />
      </div>
    </div>

    <!-- Navigation -->
    <nav class="flex-1 px-4 py-2">
      <h3 class="text-sm font-semibold text-muted-foreground uppercase mb-2">Main Menu</h3>
      <ul>
        <li>
          <a href="/" class="flex items-center p-2 bg-sidebar-accent text-sidebar-primary rounded-lg">
            <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
              <path d="M3 13h8V3H3v10zm0 8h8v-6H3v6zm10 0h8V11h-8v10zm0-18v6h8V3h-8z"/>
            </svg>
            Dashboard
          </a>
        </li>
        <li>
          <a href="/jobs" class="flex items-center p-2 text-sidebar-foreground hover:bg-sidebar-accent rounded-lg">
            <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
              <path d="M20 6h-4V4c0-1.1-.9-2-2-2h-4c-1.1 0-2 .9-2 2v2H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V8c0-1.1-.9-2-2-2zM10 4h4v2h-4V4zm10 16H4V8h16v12z"/>
            </svg>
            Jobs
          </a>
        </li>
        <li>
          <a href="/candidates" class="flex items-center p-2 text-sidebar-foreground hover:bg-sidebar-accent rounded-lg">
            <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12 12c2.7 0 5-2.2 5-5s-2.3-5-5-5-5 2.2-5 5 2.3 5 5 5zm0 2c-3.3 0-6 2.7-6 6v1h12v-1c0-3.3-2.7-6-6-6z"/>
            </svg>
            Candidates
          </a>
        </li>
        <li>
          <a href="/applications" class="flex items-center p-2 text-sidebar-foreground hover:bg-sidebar-accent rounded-lg">
            <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
              <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-5 14H7v-2h7v2zm3-4H7v-2h10v2zm0-4H7V7h10v2z"/>
            </svg>
            Applications
            <span class="ml-auto bg-sidebar-primary text-sidebar-primary-foreground text-xs font-semibold px-2 py-1 rounded-full">12</span>
          </a>
        </li>
        <li>
          <a href="/communications" class="flex items-center p-2 text-sidebar-foreground hover:bg-sidebar-accent rounded-lg">
            <Mail class="w-5 h-5 mr-2" />
            Communications
          </a>
        </li>
        <li>
          <a href="/assessments" class="flex items-center p-2 text-sidebar-foreground hover:bg-sidebar-accent rounded-lg">
            <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
              <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-7 14H7v-2h5v2zm5-4H7v-2h10v2zm0-4H7V7h10v2z"/>
            </svg>
            Assessments
          </a>
        </li>
      </ul>

      <h3 class="text-sm font-semibold text-muted-foreground uppercase mt-4 mb-2">Team</h3>
      <ul>
        <li>
          <a href="/team" class="flex items-center p-2 text-sidebar-foreground hover:bg-sidebar-accent rounded-lg">
            <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
              <path d="M16 11c1.7 0 3-1.3 3-3s-1.3-3-3-3-3 1.3-3 3 1.3 3 3 3zm-8 0c1.7 0 3-1.3 3-3S9.7 5 8 5 5 6.3 5 8s1.3 3 3 3zm0 2c-2.3 0-4.3 1.5-5 3.7V19h10v-2.3c-.7-2.2-2.7-3.7-5-3.7zm8 0c-2.3 0-4.3 1.5-5 3.7V19h10v-2.3c-.7-2.2-2.7-3.7-5-3.7z"/>
            </svg>
            Team Members
          </a>
        </li>
        <li>
          <a href="/messages" class="flex items-center p-2 text-sidebar-foreground hover:bg-sidebar-accent rounded-lg">
            <Mail class="w-5 h-5 mr-2" />
            Messages
            <span class="ml-auto bg-destructive text-destructive-foreground text-xs font-semibold px-2 py-1 rounded-full">3</span>
          </a>
        </li>
      </ul>
    </nav>

    <!-- User Profile -->
    <div class="p-4 border-t border-sidebar-border">
      <div class="flex items-center">
        <div class="w-10 h-10 rounded-full bg-sidebar-accent flex items-center justify-center">
          <User class="w-6 h-6 text-sidebar-primary" />
        </div>
        <div class="ml-3">
          <p class="text-sm font-medium text-sidebar-foreground">Jane Doe</p>
          <p class="text-xs text-muted-foreground">Senior Recruiter</p>
        </div>
        <button class="ml-auto">
          <svg class="w-5 h-5 text-muted-foreground" fill="currentColor" viewBox="0 0 24 24">
            <path d="M3 17h18v2H3v-2zm0-6h18v2H3v-2zm0-6h18v2H3V5z"/>
          </svg>
        </button>
      </div>
    </div>
  </aside>

  <!-- Main Content -->
  <div class="flex-1 flex flex-col">
    <!-- Header -->
    <header class="bg-card shadow-sm p-4 flex items-center justify-between border-b border-border">
      <h2 class="text-xl font-semibold text-foreground">Recruiter Dashboard</h2>
      <div class="flex items-center space-x-3">
        <Button variant="ghost" size="icon">
          <Bell class="w-5 h-5" />
          <span class="absolute top-0 right-0 bg-destructive text-destructive-foreground text-xs rounded-full w-5 h-5 flex items-center justify-center">2</span>
        </Button>
        <Button variant="ghost" size="icon">
          <Mail class="w-5 h-5" />
        </Button>
        <div class="w-8 h-8 rounded-full bg-sidebar-accent flex items-center justify-center">
          <User class="w-5 h-5 text-sidebar-primary" />
        </div>
      </div>
    </header>

    <!-- Main Content Area -->
    <main class="flex-1 p-6 overflow-y-auto">
      <slot />
    </main>
  </div>
</div>