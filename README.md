# Vinay N - Full Stack PHP Developer

Welcome to my GitHub portfolio! I am a **Full Stack PHP Developer** with over 6 years of experience in developing modern, scalable, and secure web applications. My expertise spans a range of technologies, including **Laravel**, **Symfony**, **Vue.js**, **MySQL**, **AWS**, and **DevOps** practices.

I thrive on delivering clean, maintainable code that solves real business problems and helps organizations grow. Whether working with back-end systems or front-end frameworks, I take pride in ensuring that each project I contribute to is of the highest quality.

## 👨‍💻 About Me
I have had the opportunity to work across diverse industries, including **healthcare**, **logistics**, and **e-commerce**. Over the years, I’ve gained a deep understanding of how web technologies can be leveraged to deliver business value. Some of my key strengths include:

- Building **HIPAA-compliant** applications for the healthcare industry
- Developing real-time systems, such as **GPS tracking dashboards** and **live video consultation platforms**
- Migrating legacy monolithic systems into **microservices architectures**
- Optimizing **performance** and ensuring **scalability** in high-traffic applications

## 🚀 My Skills

Here’s a more detailed breakdown of the technologies and tools I specialize in:

### **Backend Technologies:**
- **PHP Frameworks**: Laravel, Symfony, CodeIgniter, CakePHP, Drupal
- **Programming Languages**: PHP, Python
- **API Development**: RESTful APIs, GraphQL, WebSockets
- **Authentication**: JWT, OAuth2, Laravel Sanctum, Passport
- **Security**: XSS, SQL Injection Protection, HTTPS/SSL, Data Encryption

### **Frontend Technologies:**
- **JavaScript Frameworks**: Vue.js, React, jQuery, Livewire
- **Frontend Tools**: Tailwind CSS, Bootstrap, SASS, HTML5, CSS3
- **Libraries**: Vuex, Axios

### **Database Technologies:**
- **Relational Databases**: MySQL, MSSQL, PostgreSQL
- **NoSQL Databases**: MongoDB
- **Database Optimization**

  ### **Cloud and DevOps:**
- **Cloud Platforms**: AWS (EC2, S3, Lambda), Azure
- **Containerization**: Docker, Kubernetes
- **CI/CD**: GitHub Actions, Jenkins, Travis CI
- **Version Control**: Git, GitHub, GitLab

### **Tools & Other Technologies:**
- **IDE**: PhpStorm, VS Code, NetBeans
- **Project Management**: Jira, Agile/Scrum methodologies
- **Automation**: PHPUnit, Codeception, Selenium

## 💼 My Professional Experience

### **1. Scopic Software – PHP Developer (09/2023 to Present)**
- Developed HIPAA-compliant telemedicine platforms using **Laravel**, **Livewire**, and **Vue.js**, enabling secure real-time consultations and encrypted document sharing.
- Built **real-time GPS tracking dashboards** with **Laravel**, **Redis**, **WebSockets**, and **Google Maps API**, enabling live vehicle tracking, ETA calculations, and geofencing alerts.
- Led the transition of a legacy monolithic application into **microservices architecture**, reducing server costs by **25%**.
- Developed custom **multi-vendor e-commerce systems** with **Laravel Nova** and **Vue 3**, enhancing sales efficiency by over **30%** for clients.

### **2. Bigtincan – PHP Web Developer (02/2021 to 07/2023)**
- Worked on scaling Bigtincan's AI-powered sales enablement platform, integrating **Salesforce**, **HubSpot**, and **Google Drive** to streamline content delivery.
- Optimized **MySQL** database performance and led CRM integrations, improving **sales workflow**.
- Assisted in migrating legacy PHP applications to **Laravel** and **Symfony**, increasing maintainability and scalability.
- Participated in **Agile/Scrum** ceremonies and collaborated with the frontend team to implement **dynamic UI components**.

### **3. Cybage Software – Full Stack PHP Developer (12/2018 to 01/2020)**
- Worked for clients in the **USA healthcare sector**, troubleshooting technical issues and optimizing database queries.
- Developed **dynamic web pages** using **HTML, CSS**, and **JavaScript**, integrating with backend systems for seamless functionality.
- Managed production environments and automated tasks using **SQL jobs** and **Jenkins**.

### **4. Infonic Inc – Junior PHP Developer (10/2017 to 12/2018)**
- Assisted in creating site layouts and user interfaces using **PHP**, **HTML**, and **CSS**.
- Developed dynamic features using **JavaScript** and **jQuery** to enhance user experience.

## 🛠 Projects

### 1. **Telemedicine Platform (HIPAA-Compliant)**
Built using **Laravel**, **Vue.js**, and **Livewire**, this platform enables secure video consultations, encrypted document sharing, and comprehensive healthcare data protection. The system was designed to comply with **HIPAA** standards for privacy and security.
     
Folder Structure
telemedicine-platform/
├── backend/
│   ├── app/
│   │   ├── Http/
│   │   │   └── Controllers/
│   │   │       └── VideoCallController.php
│   ├── routes/
│   │   └── api.php
│   └── database/
│       └── migrations/
├── frontend/
│   ├── components/
│   │   └── VideoCall.vue
│   └── views/
│       └── Dashboard.vue
├── .env
├── docker-compose.yml
├── README.md
📝 Example Code
VideoCallController.php (Laravel)

namespace App\Http\Controllers;

use Illuminate\Http\Request;
use App\Models\Appointment;

class VideoCallController extends Controller
{
    public function generateToken(Request $request)
    {
        $token = bin2hex(random_bytes(32));
        return response()->json(['token' => $token]);
    }
}
VideoCall.vue (Vue.js)

<template>
  <div>
    <h3>Video Call</h3>
    <video id="localVideo" autoplay playsinline></video>
    <video id="remoteVideo" autoplay playsinline></video>
  </div>
</template>

<script>
export default {
  mounted() {
    // WebRTC code to initialize video stream
    navigator.mediaDevices.getUserMedia({ video: true, audio: true })
      .then(stream => {
        document.getElementById('localVideo').srcObject = stream;
      });
  }
}
</script>

### 2. **Real-Time GPS Tracking Dashboard**
Developed using **Laravel**, **Redis**, **WebSockets**, and **Google Maps API**, this real-time dashboard allows logistics companies to track vehicle locations, calculate estimated arrival times (ETA), and set up geofencing alerts for route management.

Folder Structure
gps-tracking-dashboard/
├── backend/
│   ├── app/
│   │   └── Http/Controllers/TrackingController.php
│   └── routes/api.php
├── frontend/
│   ├── components/MapTracker.vue
├── .env
├── README.md
📝 Example Code
TrackingController.php (Laravel)

namespace App\Http\Controllers;

use Illuminate\Http\Request;

class TrackingController extends Controller
{
    public function getVehicleLocation($id)
    {
        $location = [
            'lat' => 40.7128,
            'lng' => -74.0060,
            'status' => 'On Route'
        ];
        return response()->json($location);
    }
}
MapTracker.vue (Vue.js with Google Maps)

<template>
  <GmapMap :center="center" :zoom="12" style="height:500px;">
    <GmapMarker :position="center" />
  </GmapMap>
</template>

<script>
import { GmapMap, GmapMarker } from 'vue2-google-maps';

export default {
  components: { GmapMap, GmapMarker },
  data() {
    return { center: { lat: 40.7128, lng: -74.0060 } };
  },
  mounted() {
    setInterval(this.fetchLocation, 5000);
  },
  methods: {
    fetchLocation() {
      fetch('/api/vehicle/1/location')
        .then(res => res.json())
        .then(data => { this.center = { lat: data.lat, lng: data.lng }; });
    }
  }
}
</script>

### 3. **Multi-Vendor E-Commerce System**
Built with **Laravel Nova** and **Vue 3**, this e-commerce system supports multilingual capabilities, role-based admin controls, and real-time analytics, enabling clients to manage vendors, inventory, and transactions more effectively.

Folder Structure
ecommerce-platform/
├── backend/
│   ├── app/Http/Controllers/ProductController.php
│   ├── app/Models/Product.php
│   └── routes/api.php
├── frontend/
│   └── components/ProductList.vue
├── database/migrations/
├── README.md
📝 Example Code
ProductController.php (Laravel)

namespace App\Http\Controllers;

use App\Models\Product;
use Illuminate\Http\Request;

class ProductController extends Controller
{
    public function index()
    {
        return Product::all();
    }
}
ProductList.vue (Vue.js)

<template>
  <div>
    <h3>Products</h3>
    <ul>
      <li v-for="product in products" :key="product.id">
        {{ product.name }} - ${{ product.price }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return { products: [] };
  },
  mounted() {
    fetch('/api/products')
      .then(res => res.json())
      .then(data => { this.products = data; });
  }
}
</script>

## 🏆 Certifications

- **Microsoft Azure Fundamentals (AZ-900)**
- **Laravel, Vue.js, SASS (Udemy)**
- **AWS Cloud Practitioner Essentials (In Progress)**
- **Microsoft Azure Architect Technologies (AZ-303) (In Progress)**
- **PHP, Bootstrap, SQL Certified (Cybage Software Pvt Ltd)**

## 📚 Education

- **Double Master's Degree** in Information Technology – **Indiana Wesleyan University**, 2025
- **Master of Science** – **Kingston University**, London, UK, 2022
- **Bachelor of Science** – **Lovely Professional University**, Punjab, India, 2018

## 📫 Contact Me

- **Email**: [vinayreddynnr@gmail.com](mailto:vinayreddynnr@gmail.com)
- **LinkedIn**: [Vinay N](https://www.linkedin.com/in/vinay-n-6390071a3/)
- **GitHub**: [Vinay N's GitHub](https://github.com/vinay-n)

Feel free to check out my repositories for projects and contributions. Let’s connect and discuss how we can work together on exciting projects!

# vinaynalmela
