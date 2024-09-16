<template>
    <div class="dashboard">
      <!-- Top Header with Image and Notification -->
      <div class="header">
        <img src="@/assets/site_image.jpg" alt="Site Image" class="header-image" />
        <div class="notification-bell">
          <i class="bell-icon"></i>
          <span class="notification-count">1</span>
        </div>
      </div>
  
      <!-- Profile Section -->
      <div class="profile-section">
        <h3>Profile</h3>
        <p><strong>ID</strong>: {{ profile.id }}</p>
        <p><strong>Name</strong>: {{ profile.name }}</p>
        <p><strong>Time In</strong>: {{ profile.timeIn }}</p>
        <p><strong>Total Days</strong>: {{ profile.totalDays }}</p>
      </div>
  
      <!-- Site Overview Section -->
      <div class="site-overview">
        <h3>Site Overview</h3>
        <p><strong>Persons at site</strong>: {{ siteOverview.personsAtSite }}</p>
        <p><strong>PPE compliance</strong>: {{ siteOverview.ppeCompliance }}%</p>
        <p><strong>Safety Issues</strong>: {{ siteOverview.safetyIssues }}</p>
      </div>
  
      <!-- Recent Alerts Section -->
      <div class="recent-alerts">
        <h3>Recent Alerts</h3>
        <p><strong>Weather</strong>: {{ recentAlerts.weather }}</p>
        <p><strong>Visitors</strong>: {{ recentAlerts.visitors }}</p>
        <p><strong>Not Registered</strong>: {{ recentAlerts.notRegistered }}</p>
      </div>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    name: 'Dashboard',
    setup() {
      const profile = ref({
        id: 14464,
        name: 'John Doe',
        timeIn: '7:45am',
        totalDays: '5 Days',
      });
  
      const siteOverview = ref({
        personsAtSite: '80/100',
        ppeCompliance: 100,
        safetyIssues: 0,
      });
  
      const recentAlerts = ref({
        weather: 'Sunny',
        visitors: '5 @ 11:00 am',
        notRegistered: 0,
      });
  
      return {
        profile,
        siteOverview,
        recentAlerts,
      };
    },
  };
  </script>
  
  <style scoped>
  .dashboard {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
    padding: 20px;
    font-family: 'Arial', sans-serif;
  }
  
  .header {
    grid-column: 1 / -1;
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
  }
  
  .header-image {
    width: 50%;
    border-radius: 10px;
  }
  
  .notification-bell {
    position: relative;
  }
  
  .bell-icon {
    font-size: 24px;
  }
  
  .notification-count {
    position: absolute;
    top: -5px;
    right: -10px;
    background-color: red;
    color: white;
    border-radius: 50%;
    padding: 5px 7px;
    font-size: 12px;
  }
  
  .profile-section, .site-overview, .recent-alerts {
    background-color: #f0f0f0;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  h3 {
    margin-bottom: 15px;
    font-size: 1.2em;
    border-bottom: 2px solid black;
    display: inline-block;
    padding-bottom: 5px;
  }
  
  p {
    margin: 10px 0;
  }
  </style>
