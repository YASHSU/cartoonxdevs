import React from "react";
import Header from "../components/Header";
import Hero from "../components/Hero";
import PricingPlans from "../components/PricingPlans";
import Footer from "../components/Footer";
import { ChevronRight, Zap, ShieldCheck, Download } from "lucide-react";
import { Link } from "react-router-dom";

const Index = () => {
  return (
    <div className="min-h-screen flex flex-col">
      <Header />
      
      <main className="flex-grow">
        <Hero />
        
        {/* Features Section */}
        <section id="features" className="py-24">
          <div className="max-w-7xl mx-auto px-6">
            <div className="text-center mb-16">
              <h2 className="text-3xl md:text-4xl font-bold mb-4">
                Transform Your Photos in Seconds
              </h2>
              <p className="text-gray-600 max-w-2xl mx-auto">
                Our AI-powered platform makes it easy to turn any photo into a high-quality cartoon.
                Choose from a variety of styles to create unique artwork.
              </p>
            </div>
            
            <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
              <div className="bg-white rounded-xl p-8 shadow-sm border border-gray-100 hover:shadow-md transition-shadow">
                <div className="w-12 h-12 bg-cartoon-blue/10 rounded-lg flex items-center justify-center text-cartoon-blue-dark mb-6">
                  <Zap size={24} />
                </div>
                <h3 className="text-xl font-bold text-gray-800 mb-3">Lightning Fast</h3>
                <p className="text-gray-600">
                  Get your cartoonized images in just seconds. Our advanced AI technology processes your photos almost instantly.
                </p>
              </div>
              
              <div className="bg-white rounded-xl p-8 shadow-sm border border-gray-100 hover:shadow-md transition-shadow">
                <div className="w-12 h-12 bg-cartoon-yellow/10 rounded-lg flex items-center justify-center text-cartoon-yellow mb-6">
                  <ShieldCheck size={24} />
                </div>
                <h3 className="text-xl font-bold text-gray-800 mb-3">Secure & Private</h3>
                <p className="text-gray-600">
                  Your photos are processed securely and never shared. We respect your privacy and delete uploaded images after processing.
                </p>
              </div>
              
              <div className="bg-white rounded-xl p-8 shadow-sm border border-gray-100 hover:shadow-md transition-shadow">
                <div className="w-12 h-12 bg-cartoon-teal/10 rounded-lg flex items-center justify-center text-cartoon-teal mb-6">
                  <Download size={24} />
                </div>
                <h3 className="text-xl font-bold text-gray-800 mb-3">High Quality</h3>
                <p className="text-gray-600">
                  Download high-resolution cartoonized images perfect for printing, sharing on social media, or using in your projects.
                </p>
              </div>
            </div>
            
            <div className="mt-16 text-center">
              <Link
                to="/upload"
                className="inline-flex items-center px-6 py-3 bg-gradient-to-r from-cartoon-blue-dark to-cartoon-teal text-white font-medium rounded-lg hover:shadow-lg transform hover:-translate-y-0.5 transition-all"
              >
                Try It Now
                <ChevronRight size={18} className="ml-1" />
              </Link>
            </div>
          </div>
        </section>
        
        {/* Styles Showcase */}
        <section className="py-24 bg-gray-50">
          <div className="max-w-7xl mx-auto px-6">
            <div className="text-center mb-16">
              <h2 className="text-3xl md:text-4xl font-bold mb-4">
                Multiple Cartoon Styles
              </h2>
              <p className="text-gray-600 max-w-2xl mx-auto">
                Choose from a variety of cartoon styles to find the perfect look for your photos.
              </p>
            </div>
            
            <div className="grid grid-cols-2 md:grid-cols-4 gap-6">
              {[
                {
                  name: "Anime",
                  image: "https://images.unsplash.com/photo-1578923931302-7a176bbbbaa7?q=80&w=1374&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
                },
                {
                  name: "Sketch",
                  image: "https://images.unsplash.com/photo-1601412436967-8b2d90944ded?q=80&w=1364&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
                },
                {
                  name: "Pixar",
                  image: "https://plus.unsplash.com/premium_photo-1675186049432-edb1201e1d3a?q=80&w=987&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
                },
                {
                  name: "Comic",
                  image: "https://images.unsplash.com/photo-1541562232579-512a21360020?q=80&w=987&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
                },
              ].map((style, index) => (
                <div key={index} className="group relative overflow-hidden rounded-lg">
                  <div className="aspect-w-1 aspect-h-1 bg-gray-200">
                    <img
                      src={style.image}
                      alt={style.name}
                      className="w-full h-full object-cover transition-transform duration-300 group-hover:scale-105"
                    />
                  </div>
                  <div className="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end p-4">
                    <h4 className="text-white font-medium">{style.name} Style</h4>
                  </div>
                </div>
              ))}
            </div>
            
            <div className="mt-12 text-center">
              <Link
                to="/upload"
                className="text-cartoon-blue-dark hover:text-cartoon-teal font-medium inline-flex items-center transition-colors"
              >
                View all styles
                <ChevronRight size={16} className="ml-1" />
              </Link>
            </div>
          </div>
        </section>
        
        <PricingPlans />
      </main>
      
      <Footer />
    </div>
  );
};

export default Index;

