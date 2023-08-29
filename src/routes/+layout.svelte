
<script>
  import "../app.css";
</script>
  
  <nav class="flex items-center justify-between flex-wrap bg-white-500 py-4 px-6">
    <div class="flex items-center flex-shrink-0  mr-6">
      <img class="fill-current h-8 w-auto mr-2" src="logo-350x68-high-res.png" alt="solid-rock-logo" />
    </div>
    <div class="block lg:hidden">
      <button class="flex items-center px-3 py-2 border rounded text-white-200 border-white-400 hover:text-blue-500 hover:border-blue-500">
        <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><title>Menu</title><path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"/></svg>
      </button>
    </div>
    <div class="w-full block flex-grow lg:flex lg:items-center lg:w-auto">
      <div class="text-sm lg:flex-grow">
        <a href="/" class="block mt-4 lg:inline-block lg:mt-0 text-white-200 hover:text-sky-700 mr-4 uppercase font-bold">
          Home
        </a>
        <a href="/mission" class="block mt-4 lg:inline-block lg:mt-0 text-white-200 hover:text-sky-700 mr-4 uppercase font-bold">
          Mission
        </a>
        <a href="/staff" class="block mt-4 lg:inline-block lg:mt-0 text-white-200 hover:text-sky-700 uppercase font-bold">
          Meet the Staff
        </a>
      </div>
      <div>
        <a href="/login" class="inline-block text-sm px-4 py-2 leading-none border rounded text-teal-900 border-teal-900 hover:border-transparent hover:text-sky-500 hover:bg-stone-50 hover:border-sky-500 mt-4 lg:mt-0">Sign In</a>
      </div>
    </div>
  </nav>

<slot></slot>


