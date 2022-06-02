<script>
  async function getData() {
    const res = await fetch("https://api.github.com/users/melihuzun/repos");
    const data = await res.json();
    return data.length;
  }
</script>

{#await getData()}
  <p>test</p>
{:then data}
  <div class="stats shadow">
    <div class="stat">
      <div class="stat-figure text-primary" />
      <div class="stat-title">Repos</div>
      <div class="stat-value text-primary">{data}</div>
      <div class="stat-desc">21% more than last month</div>
    </div>

    <div class="stat">
      <div class="stat-figure text-secondary">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          class="inline-block w-8 h-8 stroke-current"
          ><path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M13 10V3L4 14h7v7l9-11h-7z"
          /></svg
        >
      </div>
      <div class="stat-title">Page Views</div>
      <div class="stat-value text-secondary">2.6M</div>
      <div class="stat-desc">21% more than last month</div>
    </div>

    <div class="stat">
      <div class="stat-figure text-secondary">
        <div class="avatar online">
          <div class="w-16 rounded-full">
            <img src="https://avatars.githubusercontent.com/u/48562450?v=4" />
          </div>
        </div>
      </div>
      <div class="stat-value">86%</div>
      <div class="stat-title">Tasks done</div>
      <div class="stat-desc text-secondary">31 tasks remaining</div>
    </div>
  </div>
{/await}
