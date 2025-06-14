
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>OpenAI Tools Hub - Free & Open Source AI Platform</title>
    <base target="_self">
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/@preline/preline@2.0.0/dist/preline.min.js"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        primary: {
                            50: '#f0f9ff',
                            100: '#e0f2fe',
                            200: '#bae6fd',
                            300: '#7dd3fc',
                            400: '#38bdf8',
                            500: '#0ea5e9',
                            600: '#0284c7',
                            700: '#0369a1',
                            800: '#075985',
                            900: '#0c4a6e',
                        }
                    }
                }
            }
        }
    </script>
    <style>
        .tool-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1);
        }
        .fade-in {
            animation: fadeIn 0.5s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        .category-btn.active {
            background-color: rgb(14, 165, 233);
            color: white;
        }
        .tool-image {
            height: 180px;
            object-fit: cover;
            width: 100%;
        }
    </style>
</head>
<body class="bg-gray-50 dark:bg-gray-900 transition-colors duration-300">
    <!-- Header -->
    <header class="sticky top-0 z-50 bg-white/80 dark:bg-gray-900/80 backdrop-blur-md border-b border-gray-200 dark:border-gray-700">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <div class="flex items-center">
                    <a href="#" class="flex items-center" id="logo-link">
                        <i class="fas fa-robot text-2xl text-primary-600 dark:text-primary-400 mr-2"></i>
                        <span class="text-xl font-bold text-gray-900 dark:text-white">OpenAI Hub</span>
                    </a>
                </div>
                <div class="flex items-center space-x-4">
                    <button id="theme-toggle" class="p-2 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-700">
                        <i class="fas fa-moon dark:hidden text-gray-700"></i>
                        <i class="fas fa-sun hidden dark:block text-yellow-300"></i>
                    </button>
                    <a href="#about" class="hidden md:inline-block px-3 py-2 text-sm font-medium text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400" id="about-link">About</a>
                    <a href="#contribute" class="hidden md:inline-block px-3 py-2 text-sm font-medium text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400" id="contribute-link">Contribute</a>
                    <a href="#tools" class="hidden md:inline-block px-3 py-2 text-sm font-medium text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400" id="tools-link">All Tools</a>
                    <button class="md:hidden p-2 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-700" id="mobile-menu-button">
                        <i class="fas fa-bars text-gray-700 dark:text-gray-300"></i>
                    </button>
                </div>
            </div>
        </div>
        
        <!-- Mobile menu -->
        <div class="md:hidden hidden" id="mobile-menu">
            <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3 bg-white dark:bg-gray-800">
                <a href="#about" class="block px-3 py-2 text-base font-medium text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400" id="mobile-about-link">About</a>
                <a href="#contribute" class="block px-3 py-2 text-base font-medium text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400" id="mobile-contribute-link">Contribute</a>
                <a href="#tools" class="block px-3 py-2 text-base font-medium text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400" id="mobile-tools-link">All Tools</a>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="bg-gradient-to-r from-primary-500 to-primary-700 dark:from-primary-700 dark:to-primary-900 text-white py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="md:flex md:items-center md:justify-between">
                <div class="md:w-1/2 mb-10 md:mb-0">
                    <h1 class="text-4xl md:text-5xl font-bold mb-6">Discover Free & Open Source AI Tools</h1>
                    <p class="text-xl mb-8 opacity-90">Your one-stop platform for the best open-source AI tools, all in one place. No paywalls, no subscriptions.</p>
                    <div class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4">
                        <a href="#tools" class="bg-white text-primary-700 hover:bg-gray-100 px-6 py-3 rounded-lg font-medium text-center transition duration-300" id="explore-btn">Explore Tools</a>
                        <a href="#contribute" class="bg-transparent border-2 border-white hover:bg-white/10 px-6 py-3 rounded-lg font-medium text-center transition duration-300" id="contribute-btn">Contribute</a>
                    </div>
                </div>
                <div class="md:w-1/2 flex justify-center">
                    <img src="https://images.unsplash.com/photo-1677442135136-760c813a743d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" 
                         alt="AI Technology" 
                         class="rounded-xl shadow-2xl w-full max-w-md border-4 border-white/20">
                </div>
            </div>
        </div>
    </section>

    <!-- Categories Section -->
    <section class="py-16 bg-gray-100 dark:bg-gray-800" id="categories">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <h2 class="text-3xl font-bold text-center mb-12 text-gray-900 dark:text-white">Browse by Category</h2>
            <div class="flex flex-wrap justify-center gap-4 mb-12" id="category-buttons">
                <!-- Categories will be added by JavaScript -->
            </div>
            <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
                <div class="bg-white dark:bg-gray-700 rounded-xl overflow-hidden shadow-md">
                    <img src="https://images.unsplash.com/photo-1620712943543-bcc4688e7485?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=765&q=80" 
                         alt="NLP" 
                         class="w-full h-32 object-cover">
                    <div class="p-4">
                        <h3 class="font-bold text-lg text-gray-900 dark:text-white">Natural Language</h3>
                        <p class="text-gray-600 dark:text-gray-300 text-sm">Text processing, generation, and analysis</p>
                    </div>
                </div>
                <div class="bg-white dark:bg-gray-700 rounded-xl overflow-hidden shadow-md">
                    <img src="https://images.unsplash.com/photo-1629904853893-c2c8981a1dc5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" 
                         alt="Computer Vision" 
                         class="w-full h-32 object-cover">
                    <div class="p-4">
                        <h3 class="font-bold text-lg text-gray-900 dark:text-white">Computer Vision</h3>
                        <p class="text-gray-600 dark:text-gray-300 text-sm">Image recognition and processing</p>
                    </div>
                </div>
                <div class="bg-white dark:bg-gray-700 rounded-xl overflow-hidden shadow-md">
                    <img src="https://images.unsplash.com/photo-1620712943543-bcc4688e7485?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=765&q=80" 
                         alt="Machine Learning" 
                         class="w-full h-32 object-cover">
                    <div class="p-4">
                        <h3 class="font-bold text-lg text-gray-900 dark:text-white">Machine Learning</h3>
                        <p class="text-gray-600 dark:text-gray-300 text-sm">Algorithms and model training</p>
                    </div>
                </div>
                <div class="bg-white dark:bg-gray-700 rounded-xl overflow-hidden shadow-md">
                    <img src="https://images.unsplash.com/photo-1629904853893-c2c8981a1dc5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" 
                         alt="Generative AI" 
                         class="w-full h-32 object-cover">
                    <div class="p-4">
                        <h3 class="font-bold text-lg text-gray-900 dark:text-white">Generative AI</h3>
                        <p class="text-gray-600 dark:text-gray-300 text-sm">Content creation and synthesis</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Tools Section -->
    <section class="py-16" id="tools">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <h2 class="text-3xl font-bold mb-12 text-center text-gray-900 dark:text-white">Featured AI Tools</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8" id="tools-container">
                <!-- Tools will be added by JavaScript -->
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="py-16 bg-gray-100 dark:bg-gray-800" id="about">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="md:flex md:items-center md:space-x-12">
                <div class="md:w-1/2 mb-10 md:mb-0">
                    <h2 class="text-3xl font-bold mb-6 text-gray-900 dark:text-white">About Open AI Hub</h2>
                    <p class="text-lg mb-4 text-gray-700 dark:text-gray-300">
                        Open AI Hub is a community-driven platform that brings together the best free and open-source AI tools in one place.
                    </p>
                    <p class="text-lg mb-6 text-gray-700 dark:text-gray-300">
                        Our mission is to make AI accessible to everyone by providing a centralized repository of tools that are free to use, modify, and distribute.
                    </p>
                    <div class="flex items-center space-x-4">
                        <div class="flex items-center">
                            <i class="fas fa-check-circle text-primary-600 dark:text-primary-400 mr-2"></i>
                            <span class="text-gray-700 dark:text-gray-300">100% Free</span>
                        </div>
                        <div class="flex items-center">
                            <i class="fas fa-check-circle text-primary-600 dark:text-primary-400 mr-2"></i>
                            <span class="text-gray-700 dark:text-gray-300">Open Source</span>
                        </div>
                        <div class="flex items-center">
                            <i class="fas fa-check-circle text-primary-600 dark:text-primary-400 mr-2"></i>
                            <span class="text-gray-700 dark:text-gray-300">Community Driven</span>
                        </div>
                    </div>
                </div>
                <div class="md:w-1/2">
                    <img src="https://images.unsplash.com/photo-1677442135136-760c813a743d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" 
                         alt="About Open AI Hub" 
                         class="rounded-xl shadow-lg w-full">
                </div>
            </div>
        </div>
    </section>

    <!-- Contribute Section -->
    <section class="py-16" id="contribute">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold mb-4 text-gray-900 dark:text-white">Contribute to the Community</h2>
                <p class="text-xl text-gray-600 dark:text-gray-300 max-w-3xl mx-auto">
                    Help us grow the collection of open-source AI tools. Submit your favorite tools or contribute to existing projects.
                </p>
            </div>
            <div class="grid md:grid-cols-3 gap-8">
                <div class="bg-white dark:bg-gray-800 p-6 rounded-xl shadow-md hover:shadow-lg transition-shadow duration-300">
                    <div class="text-primary-600 dark:text-primary-400 mb-4">
                        <i class="fas fa-code-branch text-4xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3 text-gray-900 dark:text-white">Submit a Tool</h3>
                    <p class="text-gray-600 dark:text-gray-300 mb-4">
                        Found an amazing open-source AI tool? Let us know and we'll add it to our collection.
                    </p>
                    <button class="text-primary-600 dark:text-primary-400 font-medium hover:underline" id="submit-tool-btn">Submit Tool →</button>
                </div>
                <div class="bg-white dark:bg-gray-800 p-6 rounded-xl shadow-md hover:shadow-lg transition-shadow duration-300">
                    <div class="text-primary-600 dark:text-primary-400 mb-4">
                        <i class="fas fa-code text-4xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3 text-gray-900 dark:text-white">Contribute Code</h3>
                    <p class="text-gray-600 dark:text-gray-300 mb-4">
                        Help improve existing tools by contributing code, fixing bugs, or adding new features.
                    </p>
                    <button class="text-primary-600 dark:text-primary-400 font-medium hover:underline" id="contribute-code-btn">View Projects →</button>
                </div>
                <div class="bg-white dark:bg-gray-800 p-6 rounded-xl shadow-md hover:shadow-lg transition-shadow duration-300">
                    <div class="text-primary-600 dark:text-primary-400 mb-4">
                        <i class="fas fa-book-open text-4xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3 text-gray-900 dark:text-white">Improve Documentation</h3>
                    <p class="text-gray-600 dark:text-gray-300 mb-4">
                        Good documentation is crucial. Help make these tools more accessible to everyone.
                    </p>
                    <button class="text-primary-600 dark:text-primary-400 font-medium hover:underline" id="docs-btn">View Docs →</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Newsletter Section -->
    <section class="py-16 bg-primary-600 dark:bg-primary-800 text-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="md:flex md:items-center md:justify-between">
                <div class="md:w-1/2 mb-8 md:mb-0">
                    <h2 class="text-3xl font-bold mb-4">Stay Updated</h2>
                    <p class="text-lg opacity-90">
                        Subscribe to our newsletter to get the latest open-source AI tools and updates delivered to your inbox.
                    </p>
                </div>
                <div class="md:w-1/2">
                    <form class="flex flex-col sm:flex-row gap-4" id="newsletter-form">
                        <input type="email" placeholder="Your email address" class="flex-grow px-4 py-3 rounded-lg text-gray-900 focus:outline-none focus:ring-2 focus:ring-primary-300">
                        <button type="submit" class="bg-white text-primary-700 hover:bg-gray-100 px-6 py-3 rounded-lg font-medium transition duration-300">Subscribe</button>
                    </form>
                    <p class="text-sm mt-2 opacity-80">
                        We respect your privacy. Unsubscribe at any time.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-800 text-gray-300 py-12">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
                <div>
                    <h3 class="text-white text-lg font-semibold mb-4">OpenAI Hub</h3>
                    <p class="mb-4">
                        The central platform for free and open-source AI tools.
                    </p>
                    <div class="flex space-x-4">
                        <a href="https://github.com" class="text-gray-400 hover:text-white"><i class="fab fa-github"></i></a>
                        <a href="https://twitter.com" class="text-gray-400 hover:text-white"><i class="fab fa-twitter"></i></a>
                        <a href="https://instagram.com/jeetm.patel" class="text-gray-400 hover:text-white"><i class="fab fa-instagram"></i></a>
                        <a href="https://discord.com" class="text-gray-400 hover:text-white"><i class="fab fa-discord"></i></a>
                    </div>
                </div>
                <div>
                    <h3 class="text-white text-lg font-semibold mb-4">Resources</h3>
                    <ul class="space-y-2">
                        <li><a href="#" class="hover:text-white" id="footer-tools-link">All Tools</a></li>
                        <li><a href="#" class="hover:text-white" id="footer-categories-link">Categories</a></li>
                        <li><a href="#" class="hover:text-white" id="footer-docs-link">Documentation</a></li>
                        <li><a href="#" class="hover:text-white" id="footer-blog-link">Blog</a></li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-white text-lg font-semibold mb-4">Community</h3>
                    <ul class="space-y-2">
                        <li><a href="#" class="hover:text-white" id="footer-contribute-link">Contribute</a></li>
                        <li><a href="#" class="hover:text-white" id="footer-forum-link">Forum</a></li>
                        <li><a href="https://github.com" class="hover:text-white" id="footer-github-link">GitHub</a></li>
                        <li><a href="#" class="hover:text-white" id="footer-events-link">Events</a></li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-white text-lg font-semibold mb-4">Connect</h3>
                    <ul class="space-y-2">
                        <li><a href="#" class="hover:text-white" id="footer-privacy-link">Privacy Policy</a></li>
                        <li><a href="#" class="hover:text-white" id="footer-terms-link">Terms of Service</a></li>
                        <li><a href="#" class="hover:text-white" id="footer-license-link">License</a></li>
                        <li class="flex items-center">
                            <i class="fas fa-envelope mr-2"></i>
                            <a href="mailto:contact@openaihub.com" class="hover:text-white">Email Us</a>
                        </li>
                        <li class="flex items-center">
                            <i class="fab fa-instagram mr-2"></i>
                            <a href="https://instagram.com/jeetm.patel" class="hover:text-white">@jeetm.patel</a>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="border-t border-gray-700 mt-8 pt-8 text-sm text-gray-400 text-center">
                <p>© 2023 OpenAI Hub. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Tool Modal -->
    <div id="tool-modal" class="fixed inset-0 z-50 hidden overflow-y-auto">
        <div class="flex items-center justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0">
            <div class="fixed inset-0 transition-opacity" aria-hidden="true">
                <div class="absolute inset-0 bg-gray-500 dark:bg-gray-900 opacity-75"></div>
            </div>
            <span class="hidden sm:inline-block sm:align-middle sm:h-screen" aria-hidden="true">&#8203;</span>
            <div class="inline-block align-bottom bg-white dark:bg-gray-800 rounded-lg text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-2xl sm:w-full">
                <div class="px-4 pt-5 pb-4 sm:p-6 sm:pb-4">
                    <div class="sm:flex sm:items-start">
                        <div class="mt-3 text-center sm:mt-0 sm:ml-4 sm:text-left w-full">
                            <div class="flex justify-between items-start">
                                <h3 class="text-2xl leading-6 font-bold text-gray-900 dark:text-white" id="modal-title">Tool Name</h3>
                                <button type="button" class="text-gray-400 hover:text-gray-500 dark:hover:text-gray-300" id="close-modal">
                                    <i class="fas fa-times"></i>
                                </button>
                            </div>
                            <div class="mt-4">
                                <div class="flex items-center mb-4">
                                    <span class="bg-primary-100 dark:bg-primary-900 text-primary-800 dark:text-primary-200 text-xs font-medium px-2.5 py-0.5 rounded" id="modal-category">Category</span>
                                    <span class="ml-2 text-sm text-gray-500 dark:text-gray-400" id="modal-license">License: MIT</span>
                                </div>
                                <img src="" alt="Tool Image" class="w-full h-48 object-cover rounded-lg mb-4" id="modal-image">
                                <p class="text-gray-700 dark:text-gray-300 mb-4" id="modal-description">Tool description goes here.</p>
                                <div class="mb-4">
                                    <h4 class="font-medium text-gray-900 dark:text-white mb-2">Features:</h4>
                                    <ul class="list-disc list-inside text-gray-700 dark:text-gray-300" id="modal-features">
                                        <!-- Features will be added by JavaScript -->
                                    </ul>
                                </div>
                                <div class="flex flex-wrap gap-2 mb-4" id="modal-tags">
                                    <!-- Tags will be added by JavaScript -->
                                </div>
                                <div class="flex flex-col sm:flex-row gap-4">
                                    <a href="#" class="flex-1 bg-primary-600 hover:bg-primary-700 text-white px-4 py-2 rounded-lg text-center font-medium transition duration-300" id="modal-website-btn">
                                        <i class="fas fa-globe mr-2"></i> Visit Website
                                    </a>
                                    <a href="#" class="flex-1 bg-gray-200 hover:bg-gray-300 dark:bg-gray-700 dark:hover:bg-gray-600 text-gray-800 dark:text-white px-4 py-2 rounded-lg text-center font-medium transition duration-300" id="modal-github-btn">
                                        <i class="fab fa-github mr-2"></i> GitHub
                                    </a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Data for tools with images
        const tools = [
            {
                id: 1,
                name: "Hugging Face Transformers",
                description: "State-of-the-art Natural Language Processing for PyTorch and TensorFlow",
                category: "NLP",
                license: "Apache 2.0",
                website: "https://huggingface.co/transformers",
                github: "https://github.com/huggingface/transformers",
                image: "https://images.unsplash.com/photo-1620712943543-bcc4688e7485?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=765&q=80",
                features: [
                    "Pre-trained models for NLP tasks",
                    "Easy model fine-tuning",
                    "Support for multiple frameworks",
                    "Large model repository"
                ],
                tags: ["NLP", "PyTorch", "TensorFlow", "Transformers"],
                icon: "fas fa-language"
            },
            {
                id: 2,
                name: "TensorFlow",
                description: "An end-to-end open source platform for machine learning",
                category: "Machine Learning",
                license: "Apache 2.0",
                website: "https://www.tensorflow.org",
                github: "https://github.com/tensorflow/tensorflow",
                image: "https://images.unsplash.com/photo-1629904853893-c2c8981a1dc5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80",
                features: [
                    "Comprehensive ecosystem of tools",
                    "Flexible architecture",
                    "Production-ready deployment",
                    "Strong community support"
                ],
                tags: ["Deep Learning", "Neural Networks", "Python", "Keras"],
                icon: "fas fa-brain"
            },
            {
                id: 3,
                name: "PyTorch",
                description: "An open source machine learning framework that accelerates the path from research to production",
                category: "Machine Learning",
                license: "BSD",
                website: "https://pytorch.org",
                github: "https://github.com/pytorch/pytorch",
                image: "https://images.unsplash.com/photo-1620712943543-bcc4688e7485?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=765&q=80",
                features: [
                    "Dynamic computation graphs",
                    "Strong GPU acceleration",
                    "Distributed training",
                    "Python-first approach"
                ],
                tags: ["Deep Learning", "Neural Networks", "Python", "Research"],
                icon: "fas fa-atom"
            },
            {
                id: 4,
                name: "OpenAI Gym",
                description: "A toolkit for developing and comparing reinforcement learning algorithms",
                category: "Reinforcement Learning",
                license: "MIT",
                website: "https://gym.openai.com",
                github: "https://github.com/openai/gym",
                image: "https://images.unsplash.com/photo-1629904853893-c2c8981a1dc5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80",
                features: [
                    "Variety of environments",
                    "Easy to use interface",
                    "Benchmarking tools",
                    "Compatible with major ML frameworks"
                ],
                tags: ["RL", "Simulation", "Python", "Benchmarking"],
                icon: "fas fa-robot"
            },
            {
                id: 5,
                name: "FastAPI",
                description: "A modern, fast (high-performance), web framework for building APIs with Python",
                category: "API Development",
                license: "MIT",
                website: "https://fastapi.tiangolo.com",
                github: "https://github.com/tiangolo/fastapi",
                image: "https://images.unsplash.com/photo-1620712943543-bcc4688e7485?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=765&q=80",
                features: [
                    "High performance",
                    "Easy to learn",
                    "Automatic docs",
                    "Type hints support"
                ],
                tags: ["Python", "Web", "API", "ASGI"],
                icon: "fas fa-server"
            },
            {
                id: 6,
                name: "LangChain",
                description: "Building applications with LLMs through composability",
                category: "LLM Tools",
                license: "MIT",
                website: "https://langchain.com",
                github: "https://github.com/langchain-ai/langchain",
                image: "https://images.unsplash.com/photo-1629904853893-c2c8981a1dc5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80",
                features: [
                    "LLM integration",
                    "Prompt management",
                    "Memory capabilities",
                    "Agent systems"
                ],
                tags: ["LLM", "AI", "Python", "ChatGPT"],
                icon: "fas fa-comments"
            },
            {
                id: 7,
                name: "Stable Diffusion",
                description: "A latent text-to-image diffusion model capable of generating photo-realistic images",
                category: "Image Generation",
                license: "CreativeML Open RAIL-M",
                website: "https://stablediffusionweb.com",
                github: "https://github.com/CompVis/stable-diffusion",
                image: "https://images.unsplash.com/photo-1620712943543-bcc4688e7485?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=765&q=80",
                features: [
                    "Text-to-image generation",
                    "Image-to-image translation",
                    "High-quality outputs",
                    "Customizable models"
                ],
                tags: ["AI Art", "Diffusion", "Python", "Generative"],
                icon: "fas fa-image"
            },
            {
                id: 8,
                name: "Whisper",
                description: "A general-purpose speech recognition model from OpenAI",
                category: "Speech Recognition",
                license: "MIT",
                website: "https://openai.com/research/whisper",
                github: "https://github.com/openai/whisper",
                image: "https://images.unsplash.com/photo-1629904853893-c2c8981a1dc5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80",
                features: [
                    "Multilingual support",
                    "Speech translation",
                    "Robust to background noise",
                    "Easy to use"
                ],
                tags: ["ASR", "Audio", "Python", "Translation"],
                icon: "fas fa-microphone"
            },
            {
                id: 9,
                name: "LlamaIndex",
                description: "A data framework for LLM applications to ingest, structure, and access private or domain-specific data",
                category: "LLM Tools",
                license: "MIT",
                website: "https://gpt-index.readthedocs.io",
                github: "https://github.com/jerryjliu/llama_index",
                image: "https://images.unsplash.com/photo-1620712943543-bcc4688e7485?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=765&q=80",
                features: [
                    "Data connectors",
                    "Query interfaces",
                    "Integration with LLMs",
                    "Document processing"
                ],
                tags: ["LLM", "Search", "Python", "RAG"],
                icon: "fas fa-database"
            }
        ];

        // Get unique categories
        const categories = [...new Set(tools.map(tool => tool.category))];

        // DOM elements
        const toolsContainer = document.getElementById('tools-container');
        const categoryButtons = document.getElementById('category-buttons');
        const toolModal = document.getElementById('tool-modal');
        const closeModal = document.getElementById('close-modal');
        const themeToggle = document.getElementById('theme-toggle');
        const mobileMenuButton = document.getElementById('mobile-menu-button');
        const mobileMenu = document.getElementById('mobile-menu');

        // Initialize the page
        document.addEventListener('DOMContentLoaded', function() {
            // Render all tools
            renderTools(tools);
            
            // Render category buttons
            renderCategoryButtons();
            
            // Set up event listeners
            setupEventListeners();
            
            // Check for dark mode preference
            checkDarkModePreference();
        });

        // Render tools with images
        function renderTools(toolsToRender) {
            toolsContainer.innerHTML = '';
            
            toolsToRender.forEach(tool => {
                const toolCard = document.createElement('div');
                toolCard.className = 'tool-card bg-white dark:bg-gray-800 rounded-xl shadow-md overflow-hidden transition-all duration-300 fade-in';
                toolCard.innerHTML = `
                    <img src="${tool.image}" alt="${tool.name}" class="tool-image">
                    <div class="p-6">
                        <div class="flex items-center mb-4">
                            <div class="bg-primary-100 dark:bg-primary-900 p-3 rounded-lg mr-4">
                                <i class="${tool.icon} text-primary-600 dark:text-primary-400 text-xl"></i>
                            </div>
                            <div>
                                <h3 class="text-xl font-bold text-gray-900 dark:text-white">${tool.name}</h3>
                                <span class="text-sm text-gray-500 dark:text-gray-400">${tool.category}</span>
                            </div>
                        </div>
                        <p class="text-gray-700 dark:text-gray-300 mb-4">${tool.description}</p>
                        <div class="flex flex-wrap gap-2 mb-4">
                            ${tool.tags.map(tag => `<span class="bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-gray-200 text-xs px-2.5 py-0.5 rounded">${tag}</span>`).join('')}
                        </div>
                        <button class="w-full bg-primary-600 hover:bg-primary-700 text-white px-4 py-2 rounded-lg font-medium transition duration-300 view-tool-btn" data-id="${tool.id}">
                            View Details
                        </button>
                    </div>
                `;
                toolsContainer.appendChild(toolCard);
            });
            
            // Add event listeners to view buttons
            document.querySelectorAll('.view-tool-btn').forEach(button => {
                button.addEventListener('click', function() {
                    const toolId = parseInt(this.getAttribute('data-id'));
                    const tool = tools.find(t => t.id === toolId);
                    if (tool) {
                        openToolModal(tool);
                    }
                });
            });
        }

        // Render category buttons
        function renderCategoryButtons() {
            categoryButtons.innerHTML = '';
            
            // Add "All" button
            const allButton = document.createElement('button');
            allButton.className = 'category-btn active px-4 py-2 rounded-lg bg-primary-600 text-white';
            allButton.textContent = 'All';
            allButton.addEventListener('click', function() {
                document.querySelectorAll('.category-btn').forEach(btn => btn.classList.remove('active'));
                this.classList.add('active');
                renderTools(tools);
            });
            categoryButtons.appendChild(allButton);
            
            // Add category buttons
            categories.forEach(category => {
                const button = document.createElement('button');
                button.className = 'category-btn px-4 py-2 rounded-lg bg-gray-200 dark:bg-gray-700 text-gray-800 dark:text-gray-200 hover:bg-gray-300 dark:hover:bg-gray-600';
                button.textContent = category;
                button.addEventListener('click', function() {
                    document.querySelectorAll('.category-btn').forEach(btn => btn.classList.remove('active'));
                    this.classList.add('active');
                    const filteredTools = tools.filter(tool => tool.category === category);
                    renderTools(filteredTools);
                });
                categoryButtons.appendChild(button);
            });
        }

        // Open tool modal with image
        function openToolModal(tool) {
            document.getElementById('modal-title').textContent = tool.name;
            document.getElementById('modal-category').textContent = tool.category;
            document.getElementById('modal-license').textContent = `License: ${tool.license}`;
            document.getElementById('modal-description').textContent = tool.description;
            document.getElementById('modal-image').src = tool.image;
            document.getElementById('modal-image').alt = tool.name;
            
            // Set features
            const featuresList = document.getElementById('modal-features');
            featuresList.innerHTML = '';
            tool.features.forEach(feature => {
                const li = document.createElement('li');
                li.textContent = feature;
                featuresList.appendChild(li);
            });
            
            // Set tags
            const tagsContainer = document.getElementById('modal-tags');
            tagsContainer.innerHTML = '';
            tool.tags.forEach(tag => {
                const span = document.createElement('span');
                span.className = 'bg-gray-100 dark:bg-gray-700 text-gray-800 dark:text-gray-200 text-xs px-2.5 py-0.5 rounded';
                span.textContent = tag;
                tagsContainer.appendChild(span);
            });
            
            // Set buttons
            document.getElementById('modal-website-btn').setAttribute('href', tool.website);
            document.getElementById('modal-github-btn').setAttribute('href', tool.github);
            
            // Show modal
            toolModal.classList.remove('hidden');
        }

        // Close tool modal
        function closeToolModal() {
            toolModal.classList.add('hidden');
        }

        // Check dark mode preference
        function checkDarkModePreference() {
            if (localStorage.getItem('color-theme') === 'dark' || (!('color-theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
                document.documentElement.classList.add('dark');
            } else {
                document.documentElement.classList.remove('dark');
            }
        }

        // Toggle dark mode
        function toggleDarkMode() {
            if (localStorage.getItem('color-theme')) {
                if (localStorage.getItem('color-theme') === 'light') {
                    document.documentElement.classList.add('dark');
                    localStorage.setItem('color-theme', 'dark');
                } else {
                    document.documentElement.classList.remove('dark');
                    localStorage.setItem('color-theme', 'light');
                }
            } else {
                if (document.documentElement.classList.contains('dark')) {
                    document.documentElement.classList.remove('dark');
                    localStorage.setItem('color-theme', 'light');
                } else {
                    document.documentElement.classList.add('dark');
                    localStorage.setItem('color-theme', 'dark');
                }
            }
        }

        // Toggle mobile menu
        function toggleMobileMenu() {
            mobileMenu.classList.toggle('hidden');
        }

        // Handle navigation
        function handleNavigation(e) {
            e.preventDefault();
            const targetId = this.getAttribute('href');
            const targetElement = document.querySelector(targetId);
            if (targetElement) {
                targetElement.scrollIntoView({ behavior: 'smooth' });
            }
            
            // Close mobile menu if open
            if (!mobileMenu.classList.contains('hidden')) {
                mobileMenu.classList.add('hidden');
            }
        }

        // Set up event listeners
        function setupEventListeners() {
            // Modal
            closeModal.addEventListener('click', closeToolModal);
            
            // Theme toggle
            themeToggle.addEventListener('click', toggleDarkMode);
            
            // Mobile menu
            mobileMenuButton.addEventListener('click', toggleMobileMenu);
            
            // Navigation links
            const navLinks = [
                'logo-link', 'about-link', 'contribute-link', 'tools-link',
                'mobile-about-link', 'mobile-contribute-link', 'mobile-tools-link',
                'explore-btn', 'contribute-btn', 'submit-tool-btn', 'contribute-code-btn', 'docs-btn',
                'footer-tools-link', 'footer-categories-link', 'footer-docs-link', 'footer-blog-link',
                'footer-contribute-link', 'footer-forum-link', 'footer-github-link', 'footer-events-link',
                'footer-privacy-link', 'footer-terms-link', 'footer-license-link'
            ];
            
            navLinks.forEach(id => {
                const element = document.getElementById(id);
                if (element) {
                    element.addEventListener('click', handleNavigation);
                }
            });
            
            // Newsletter form
            const newsletterForm = document.getElementById('newsletter-form');
            if (newsletterForm) {
                newsletterForm.addEventListener('submit', function(e) {
                    e.preventDefault();
                    const emailInput = this.querySelector('input[type='email']');
                    if (emailInput.value) {
                        alert('Thank you for subscribing to our newsletter!');
                        emailInput.value = '';
                    }
                });
            }
            
            // Instagram link
            const instagramLinks = document.querySelectorAll('a[href*="instagram.com/jeetm.patel"]');
            instagramLinks.forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    window.open('https://instagram.com/jeetm.patel', '_blank');
                });
            });
        }
    </script>
</body>
</html>
