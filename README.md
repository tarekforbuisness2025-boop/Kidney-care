<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nephrology & Kidney Care Center</title>
    <!-- Load Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Configure Tailwind for custom colors and Inter font -->
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');
        body {
            font-family: 'Inter', sans-serif;
        }
        .icon {
            width: 24px;
            height: 24px;
            fill: none;
            stroke-width: 2;
            stroke-linecap: round;
            stroke-linejoin: round;
        }
    </style>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'primary-blue': '#0369a1', // Sky-700 equivalent
                        'secondary-teal': '#0d9488', // Teal-600 equivalent
                    }
                }
            }
        }
    </script>
</head>
<body class="bg-gray-50">

    <!-- Scroll to element function -->
    <script>
        function scrollToSection(id) {
            document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
            // Close mobile menu if open
            document.getElementById('mobile-menu').classList.add('hidden');
        }

        // Simple form submission handler (client-side only)
        function handleConsultationSubmit(event) {
            event.preventDefault();
            const form = event.target;
            const messageBox = document.getElementById('form-message');
            
            // Collect form data (for display purposes)
            const name = form.name.value;
            
            messageBox.textContent = `Thank you, ${name}! Your consultation request has been received. We will contact you shortly.`;
            messageBox.classList.remove('hidden');
            form.reset();
            
            // Auto-hide message after 5 seconds
            setTimeout(() => {
                messageBox.classList.add('hidden');
            }, 5000);
        }
    </script>

    <!-- Header & Navigation -->
    <header class="sticky top-0 z-50 bg-white shadow-md">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <!-- Logo -->
                <a href="#" class="flex items-center space-x-2">
                    <!-- SVG Kidney Icon -->
                    <svg class="icon w-8 h-8 stroke-primary-blue" viewBox="0 0 24 24">
                        <path d="M5 22h14"/>
                        <path d="M5 2h14"/>
                        <path d="M12 22v-4"/>
                        <path d="M12 2v4"/>
                        <path d="M12 6c4 0 5 3 5 5v3c0 1.5-1 2-2 2h-6c-1 0-2-0.5-2-2v-3c0-2 1-5 5-5z"/>
                    </svg>
                    <span class="text-xl font-extrabold text-gray-800">Kidney<span class="text-primary-blue">Care</span></span>
                </a>

                <!-- Desktop Navigation -->
                <nav class="hidden md:flex space-x-8">
                    <a href="#hero" onclick="scrollToSection('hero')" class="text-gray-600 hover:text-primary-blue transition duration-150 font-medium">Home</a>
                    <a href="#services" onclick="scrollToSection('services')" class="text-gray-600 hover:text-primary-blue transition duration-150 font-medium">Services</a>
                    <a href="#about" onclick="scrollToSection('about')" class="text-gray-600 hover:text-primary-blue transition duration-150 font-medium">About Us</a>
                    <a href="#consultation" onclick="scrollToSection('consultation')" class="text-primary-blue border border-primary-blue px-4 py-1.5 rounded-full hover:bg-primary-blue hover:text-white transition duration-200 shadow-lg">Book Now</a>
                </nav>

                <!-- Mobile Menu Button -->
                <button id="menu-button" class="md:hidden text-gray-600 focus:outline-none" aria-label="Open menu" onclick="document.getElementById('mobile-menu').classList.toggle('hidden');">
                    <!-- SVG Menu Icon -->
                    <svg class="icon w-6 h-6 stroke-primary-blue" viewBox="0 0 24 24">
                        <path d="M3 12h18M3 6h18M3 18h18"/>
                    </svg>
                </button>
            </div>
        </div>

        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-white shadow-xl absolute w-full pb-3 border-t border-gray-100">
            <div class="px-2 pt-2 space-y-1 sm:px-3 flex flex-col items-center">
                <a href="#hero" onclick="scrollToSection('hero')" class="block w-full text-center px-3 py-2 text-base font-medium text-gray-700 hover:bg-gray-50 rounded-lg">Home</a>
                <a href="#services" onclick="scrollToSection('services')" class="block w-full text-center px-3 py-2 text-base font-medium text-gray-700 hover:bg-gray-50 rounded-lg">Services</a>
                <a href="#about" onclick="scrollToSection('about')" class="block w-full text-center px-3 py-2 text-base font-medium text-gray-700 hover:bg-gray-50 rounded-lg">About Us</a>
                <a href="#consultation" onclick="scrollToSection('consultation')" class="block w-3/4 text-center mt-3 px-3 py-2 text-base font-medium text-white bg-primary-blue rounded-full hover:bg-sky-800 transition duration-150">Book Now</a>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="hero" class="py-20 md:py-32 bg-primary-blue text-white overflow-hidden shadow-2xl">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="lg:grid lg:grid-cols-12 lg:gap-8">
                <div class="col-span-7 flex flex-col justify-center text-center lg:text-left">
                    <h1 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold leading-tight tracking-tight">
                        Expert Nephrology Care, <br class="hidden lg:inline"/>
                        <span class="text-secondary-teal">Focused on Your Kidney Health.</span>
                    </h1>
                    <p class="mt-6 text-lg sm:text-xl text-sky-100 max-w-xl mx-auto lg:mx-0">
                        We provide specialized diagnosis and treatment for all kidney-related diseases, hypertension, and fluid imbalances.
                    </p>
                    <div class="mt-10 flex justify-center lg:justify-start">
                        <a href="#consultation" onclick="scrollToSection('consultation')" class="inline-block bg-secondary-teal text-white text-lg font-semibold px-8 py-3 rounded-full hover:bg-teal-700 transition duration-300 transform hover:scale-105 shadow-xl">
                            Request a Consultation
                        </a>
                    </div>
                </div>
                <div class="hidden lg:block col-span-5 relative">
                    <!-- Placeholder image: Doctor/Kidney diagram -->
                    <img src="https://placehold.co/400x400/0d9488/ffffff?text=Specialist+Nephrologist" 
                         alt="Specialist Nephrologist providing care" 
                         class="rounded-3xl shadow-2xl object-cover transform translate-y-10" 
                         onerror="this.onerror=null; this.src='https://placehold.co/400x400/0d9488/ffffff?text=Doctor+Care';">
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-16 md:py-24 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center">
                <h2 class="text-3xl sm:text-4xl font-extrabold text-gray-800">Our Comprehensive Kidney Services</h2>
                <p class="mt-4 text-xl text-gray-500">Dedicated care across the full spectrum of renal medicine.</p>
            </div>
            
            <div class="mt-12 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                
                <!-- Service Card 1: CKD Management -->
                <div class="bg-gray-50 p-6 rounded-2xl shadow-lg border border-gray-100 hover:shadow-xl transition duration-300">
                    <div class="flex items-center space-x-4">
                        <!-- Kidney Icon -->
                        <div class="p-3 bg-primary-blue/10 rounded-xl">
                            <svg class="icon w-6 h-6 stroke-primary-blue" viewBox="0 0 24 24"><path d="M22 17a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V7a2 2 0 0 1 2-2h16a2 2 0 0 1 2 2z"/><path d="M12 12c2.2 0 4-1.8 4-4s-1.8-4-4-4-4 1.8-4 4 1.8 4 4 4zM10 12h4m-2 2v-4"/></svg>
                        </div>
                        <h3 class="text-xl font-semibold text-gray-900">Chronic Kidney Disease (CKD)</h3>
                    </div>
                    <p class="mt-4 text-gray-600">Personalized treatment plans, lifestyle management, and risk reduction strategies for slowing the progression of CKD.</p>
                </div>

                <!-- Service Card 2: Dialysis -->
                <div class="bg-gray-50 p-6 rounded-2xl shadow-lg border border-gray-100 hover:shadow-xl transition duration-300">
                    <div class="flex items-center space-x-4">
                        <!-- Treatment Icon -->
                        <div class="p-3 bg-secondary-teal/10 rounded-xl">
                            <svg class="icon w-6 h-6 stroke-secondary-teal" viewBox="0 0 24 24"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><path d="M14 2v6h6"/><path d="M12 18v-6"/></svg>
                        </div>
                        <h3 class="text-xl font-semibold text-gray-900">Dialysis Management</h3>
                    </div>
                    <p class="mt-4 text-gray-600">Expert coordination and ongoing care for Hemodialysis and Peritoneal Dialysis patients.</p>
                </div>

                <!-- Service Card 3: Hypertension -->
                <div class="bg-gray-50 p-6 rounded-2xl shadow-lg border border-gray-100 hover:shadow-xl transition duration-300">
                    <div class="flex items-center space-x-4">
                        <!-- Heart/Pressure Icon -->
                        <div class="p-3 bg-primary-blue/10 rounded-xl">
                            <svg class="icon w-6 h-6 stroke-primary-blue" viewBox="0 0 24 24"><path d="M19 14c1.49-1.46 3-3.21 3-5.5A5.5 5.5 0 0 0 16.5 3c-1.76 0-3 .5-4.5 2-1.5-1.5-2.74-2-4.5-2A5.5 5.5 0 0 0 2 8.5c0 2.3 1.5 4.05 3 5.5l7 7Z"/></svg>
                        </div>
                        <h3 class="text-xl font-semibold text-gray-900">Renal Hypertension</h3>
                    </div>
                    <p class="mt-4 text-gray-600">Diagnosis and specialized management of high blood pressure caused or complicated by kidney issues.</p>
                </div>
                
                <!-- Service Card 4: Kidney Stones -->
                <div class="bg-gray-50 p-6 rounded-2xl shadow-lg border border-gray-100 hover:shadow-xl transition duration-300">
                    <div class="flex items-center space-x-4">
                        <!-- Stone/Pain Icon -->
                        <div class="p-3 bg-secondary-teal/10 rounded-xl">
                            <svg class="icon w-6 h-6 stroke-secondary-teal" viewBox="0 0 24 24"><path d="M14.7 10.7c.3-.3.3-.8 0-1.1l-2.4-2.4c-.3-.3-.8-.3-1.1 0L4 16.2V20h3.8l7.9-7.9z"/><path d="M20 7L17 4l-3 3"/></svg>
                        </div>
                        <h3 class="text-xl font-semibold text-gray-900">Kidney Stone Prevention</h3>
                    </div>
                    <p class="mt-4 text-gray-600">Metabolic workup and dietary advice to prevent recurrent stone formation.</p>
                </div>
                
                <!-- Service Card 5: Transplant Care -->
                <div class="bg-gray-50 p-6 rounded-2xl shadow-lg border border-gray-100 hover:shadow-xl transition duration-300">
                    <div class="flex items-center space-x-4">
                        <!-- Hand/Support Icon -->
                        <div class="p-3 bg-primary-blue/10 rounded-xl">
                            <svg class="icon w-6 h-6 stroke-primary-blue" viewBox="0 0 24 24"><path d="M12 2a3 3 0 0 0-3 3v.17c0 .41-.12.82-.35 1.17l-.87 1.3A3 3 0 0 0 7 11v6H4c-1.1 0-2 .9-2 2v2a2 2 0 0 0 2 2h16c1.1 0 2-.9 2-2v-2c0-1.1-.9-2-2-2h-3v-6c0-1.28-.5-2.5-1.35-3.35l-.87-1.3c-.23-.35-.76-.35-1.17V5a3 3 0 0 0-3-3zM12 8h0"/></svg>
                        </div>
                        <h3 class="text-xl font-semibold text-gray-900">Post-Transplant Care</h3>
                    </div>
                    <p class="mt-4 text-gray-600">Immunosuppression management and long-term follow-up for kidney transplant recipients.</p>
                </div>
                
                <!-- Service Card 6: Electrolyte Disorders -->
                <div class="bg-gray-50 p-6 rounded-2xl shadow-lg border border-gray-100 hover:shadow-xl transition duration-300">
                    <div class="flex items-center space-x-4">
                        <!-- Test Tube/Lab Icon -->
                        <div class="p-3 bg-secondary-teal/10 rounded-xl">
                            <svg class="icon w-6 h-6 stroke-secondary-teal" viewBox="0 0 24 24"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><path d="M14 2v6h6"/></svg>
                        </div>
                        <h3 class="text-xl font-semibold text-gray-900">Electrolyte Disorders</h3>
                    </div>
                    <p class="mt-4 text-gray-600">Diagnosis and correction of complex salt, water, and acid-base balance issues.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-16 md:py-24 bg-primary-blue/5">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="lg:grid lg:grid-cols-12 lg:gap-12">
                
                <!-- Image Placeholder -->
                <div class="lg:col-span-5 mb-8 lg:mb-0">
                    <img src="https://placehold.co/400x500/0369a1/ffffff?text=Dr.+Tarek+Algamal" 
                         alt="Lead Nephrologist Dr. Tarek Algamal" 
                         class="rounded-3xl shadow-2xl object-cover w-full h-auto lg:h-full"
                         onerror="this.onerror=null; this.src='https://placehold.co/400x500/0369a1/ffffff?text=Doctor+Profile';">
                </div>
                
                <!-- Content -->
                <div class="lg:col-span-7 flex flex-col justify-center">
                    <span class="text-primary-blue text-sm font-semibold uppercase tracking-wider">Meet Our Specialist</span>
                    <h2 class="mt-2 text-3xl sm:text-4xl font-extrabold text-gray-800">Driven by Compassion, Guided by Expertise</h2>
                    <p class="mt-6 text-lg text-gray-600">
                        At KidneyCare Center, our practice is led by **Dr. Tarek Algamal**, a board-certified Nephrologist with over 15 years of experience in leading kidney health and transplant programs. His philosophy centers on **preventative care** and **patient empowerment**, ensuring you understand every step of your treatment journey.
                    </p>
                    <p class="mt-4 text-lg text-gray-600">
                        We use the latest diagnostic technology to accurately assess renal function and tailor sophisticated, evidence-based treatments, from managing early-stage Chronic Kidney Disease to preparing for advanced therapeutic interventions. Your long-term well-being is our primary focus.
                    </p>
                    
                    <div class="mt-8 flex items-center space-x-6">
                        <div class="text-center">
                            <p class="text-3xl font-bold text-primary-blue">15+</p>
                            <p class="text-gray-600">Years of Experience</p>
                        </div>
                        <div class="text-center">
                            <p class="text-3xl font-bold text-primary-blue">98%</p>
                            <p class="text-gray-600">Patient Satisfaction</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Consultation/Contact Section -->
    <section id="consultation" class="py-16 md:py-24 bg-primary-blue text-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center">
                <h2 class="text-3xl sm:text-4xl font-extrabold">Ready to take control of your health?</h2>
                <p class="mt-4 text-xl text-sky-100">Schedule your specialized nephrology consultation today.</p>
            </div>
            
            <div class="mt-12 max-w-lg mx-auto bg-white p-6 sm:p-10 rounded-3xl shadow-2xl">
                <p id="form-message" class="hidden text-center p-3 mb-4 bg-secondary-teal text-white font-medium rounded-xl transition duration-300"></p>

                <form onsubmit="handleConsultationSubmit(event)" class="space-y-6">
                    <div>
                        <label for="name" class="block text-sm font-medium text-gray-700">Full Name</label>
                        <input type="text" id="name" name="name" required 
                               class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-lg shadow-sm focus:ring-secondary-teal focus:border-secondary-teal text-gray-900 placeholder-gray-400">
                    </div>
                    
                    <div>
                        <label for="email" class="block text-sm font-medium text-gray-700">Email Address</label>
                        <input type="email" id="email" name="email" required 
                               class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-lg shadow-sm focus:ring-secondary-teal focus:border-secondary-teal text-gray-900 placeholder-gray-400">
                    </div>
                    
                    <div>
                        <label for="phone" class="block text-sm font-medium text-gray-700">Phone Number</label>
                        <input type="tel" id="phone" name="phone" required 
                               class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-lg shadow-sm focus:ring-secondary-teal focus:border-secondary-teal text-gray-900 placeholder-gray-400">
                    </div>

                    <div>
                        <label for="symptoms" class="block text-sm font-medium text-gray-700">Reason for Consultation (Briefly)</label>
                        <textarea id="symptoms" name="symptoms" rows="4" required 
                                  class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-lg shadow-sm focus:ring-secondary-teal focus:border-secondary-teal text-gray-900 placeholder-gray-400"></textarea>
                    </div>
                    
                    <div>
                        <button type="submit" class="w-full flex justify-center py-3 px-4 border border-transparent rounded-full shadow-lg text-lg font-medium text-white bg-secondary-teal hover:bg-teal-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-secondary-teal transition duration-200 transform hover:scale-[1.02]">
                            Submit Request
                        </button>
                    </div>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 py-12">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-white">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
                
                <!-- Clinic Info -->
                <div>
                    <h4 class="text-xl font-bold text-primary-blue mb-4">KidneyCare Center</h4>
                    <p class="text-gray-400 text-sm">Dedicated to excellence in kidney disease management and preventative care.</p>
                </div>

                <!-- Quick Links -->
                <div>
                    <h4 class="text-lg font-semibold mb-4">Quick Links</h4>
                    <ul class="space-y-2">
                        <li><a href="#services" onclick="scrollToSection('services')" class="text-gray-400 hover:text-primary-blue transition duration-150">Services</a></li>
                        <li><a href="#about" onclick="scrollToSection('about')" class="text-gray-400 hover:text-primary-blue transition duration-150">Our Team</a></li>
                        <li><a href="#consultation" onclick="scrollToSection('consultation')" class="text-gray-400 hover:text-primary-blue transition duration-150">Book Appointment</a></li>
                    </ul>
                </div>

                <!-- Contact -->
                <div>
                    <h4 class="text-lg font-semibold mb-4">Contact Details</h4>
                    <p class="text-gray-400 flex items-center mb-2">
                        <!-- Phone Icon -->
                        <svg class="icon w-4 h-4 mr-2 stroke-secondary-teal" viewBox="0 0 24 24"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.63A2 2 0 0 1 3.08 2h3a2 2 0 0 1 2 1.72 17.65 17.65 0 0 0 .39 3.2 2 2 0 0 1-1.07 2.15l-1.09.73a19.5 19.5 0 0 0 6 6l.73-1.09a2 2 0 0 1 2.15-1.07 17.65 17.65 0 0 0 3.2.39 2 2 0 0 1 1.72 2z"/></svg>
                        (555) 123-4567
                    </p>
                    <p class="text-gray-400 flex items-center">
                        <!-- Mail Icon -->
                        <svg class="icon w-4 h-4 mr-2 stroke-secondary-teal" viewBox="0 0 24 24"><rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
                        info@kidneycare.com
                    </p>
                </div>

                <!-- Service Area (Replaced Location) -->
                <div>
                    <h4 class="text-lg font-semibold mb-4">Service Area</h4>
                    <p class="text-gray-400">
                        **Virtual Nephrology Practice**<br>
                        Serving patients nationwide via secure telemedicine.<br>
                        *(Check licensing for specific states)*
                    </p>
                </div>
            </div>

            <div class="mt-12 pt-8 border-t border-gray-700 text-center">
                <p class="text-sm text-gray-500">&copy; 2025 KidneyCare Center. All rights reserved.</p>
            </div>
        </div>
    </footer>

</body>
</html>eatment, electrolyte disorders, dialysis planning and all consultations related to kidney health entirely via secure telemedicine. 
