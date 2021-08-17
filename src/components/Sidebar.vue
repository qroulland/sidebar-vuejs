<template>
    <div
      class="bg-gray-900 h-screen min-h-screen py-8 px-6 relative"
      :class="expanded ? 'w-1/6' : 'w-32 flex items-center flex-col'"
    >
        <div class="text-white flex items-center justify-between mb-6">
            <h1 v-if="expanded" class="text-2xl font-bold">Dashboard</h1>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-8 w-8 transform hover:scale-150 duration-500"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              @click="expanded = !expanded"
            >
                <path
                    strokeLinecap="round"
                    strokeLinejoin="round"
                    strokeWidth={2}
                    d="M4 6h16M4 12h16M4 18h16"
                />
            </svg>
        </div>
        <div class="bg-gray-600 rounded-md p-3 flex text-white">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path
                    strokeLinecap="round"
                    strokeLinejoin="round"
                    strokeWidth={2}
                    d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
                />
            </svg>
            <span v-if="expanded" class="ml-3">
                Search...
            </span>
        </div>
        <div class="my-6">
            <div v-if="expanded" class="text-gray-300 text-sm font-semibold mb-3">
                Navigation
            </div>
            <menu-item
              label="Dashboard"
              :current="current === 'Dashboard'"
              :expanded="expanded"
            >
                <template v-slot:icon>
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path
                            strokeLinecap="round"
                            strokeLinejoin="round"
                            strokeWidth={2}
                            d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"
                        />
                    </svg>
                </template>
            </menu-item>
            <menu-item
              label="Messenger"
              :current="current === 'Messenger'"
              :expanded="expanded"
            >
                <template v-slot:icon>
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path
                        strokeLinecap="round"
                        strokeLinejoin="round"
                        strokeWidth={2}
                        d="M17 8h2a2 2 0 012 2v6a2 2 0 01-2 2h-2v4l-4-4H9a1.994 1.994 0 01-1.414-.586m0 0L11 14h4a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2v4l.586-.586z"
                      />
                    </svg>
                </template>
            </menu-item>
            <menu-item
              label="Analytics"
              :current="current === 'Analytics'"
              :expanded="expanded"
            >
                <template v-slot:icon>
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z" />
                    </svg>
                </template>
            </menu-item>
            <menu-item
              label="Calendar"
              :current="current === 'Calendar'"
              :expanded="expanded"
            >
                <template v-slot:icon>
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z" />
                    </svg>
                </template>
            </menu-item>
            <menu-item
              label="Schedules"
              :current="current === 'Schedules'"
              :expanded="expanded"
            >
                <template v-slot:icon>
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
                    </svg>
                </template>
            </menu-item>
            <menu-item
              label="Users"
              :current="current === 'Users'"
              :expanded="expanded"
            >
                <template v-slot:icon>
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z" />
                    </svg>
                </template>
            </menu-item>
            <menu-item
              label="File manager"
              :current="current === 'File manager'"
              :expanded="expanded"
            >
                <template v-slot:icon>
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M5 19a2 2 0 01-2-2V7a2 2 0 012-2h4l2 2h4a2 2 0 012 2v1M5 19h14a2 2 0 002-2v-5a2 2 0 00-2-2H9a2 2 0 00-2 2v5a2 2 0 01-2 2z" />
                    </svg>
                </template>
            </menu-item>
            <menu-item
              label="Settings"
              :current="current === 'Settings'"
              :expanded="expanded"
            >
                <template v-slot:icon>
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" />
                      <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
                    </svg>
                </template>
            </menu-item>
        </div>
        <div
          class="flex items-center absolute bottom-8 -mx-6 px-6 w-full"
          :class="expanded ? 'justify-between' : 'justify-center' "
        >
          <div class="rounded-md bg-gray-500 p-3 text-white">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
            </svg>
          </div>
          <div v-if="expanded" class="flex flex-col text-white">
            <span class="text-sm text-gray-300">
              Hello
            </span>
            <span>
              Nikoloz Ergemlidze
            </span>
          </div>
          <div v-if="expanded" class="bg-gray-500 p-2 rounded-md hover:bg-blue-600 hover:text-white">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-3 w-3" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M9 5l7 7-7 7" />
            </svg>
          </div>
        </div>
    </div>
</template>

<script>
import MenuItem from '@/components/MenuItem.vue';

export default {
  name: 'Home',
  components: {
    MenuItem,
  },
  data() {
    return {
      current: 'Dashboard',
      expanded: true,
    };
  },
};
</script>
