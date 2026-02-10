# creative
import { Link } from "react-router-dom";
import { ArrowRight, Sparkles } from "lucide-react";
import { Button } from "@/components/ui/button";
import { Layout } from "@/components/layout/Layout";
import heroBg from "@/assets/hero-bg.jpg";
import logo1 from "@/assets/portfolio/logo-1.jpg";
import poster1 from "@/assets/portfolio/poster-1.jpg";
import branding1 from "@/assets/portfolio/branding-1.jpg";

const featuredWork = [
  { id: 1, title: "Brand Identity", category: "Logo Design", image: logo1 },
  { id: 2, title: "Event Poster", category: "Print Design", image: poster1 },
  { id: 3, title: "Corporate Branding", category: "Branding", image: branding1 },
];

const stats = [
  { value: "50+", label: "Projects Completed" },
  { value: "5+", label: "Years Experience" },
  { value: "30+", label: "Happy Clients" },
];

const Index = () => {
  return (
    <Layout>
      {/* Hero Section */}
      <section className="relative min-h-screen flex items-center justify-center overflow-hidden">
        {/* Background Image with Overlay */}
        <div className="absolute inset-0">
          <img 
            src={heroBg} 
            alt="Creative background" 
            className="w-full h-full object-cover"
          />
          <div className="absolute inset-0 hero-gradient opacity-90" />
        </div>

        {/* Hero Content */}
        <div className="relative z-10 container-custom text-center">
          <div className="max-w-4xl mx-auto stagger-children">
            {/* Badge */}
            <div className="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-white/10 backdrop-blur-sm text-white/80 text-sm mb-8 opacity-0">
              <Sparkles className="h-4 w-4 text-accent" />
              <span>Stevenson Creatives — Design & Branding</span>
            </div>

            {/* Main Headline */}
            <h1 className="text-4xl md:text-6xl lg:text-7xl font-bold text-white leading-tight mb-6 opacity-0 text-balance">
              Crafting Visual
              <br />
              <span className="text-gradient">Experiences</span> That
              <br />
              Inspire
            </h1>

            {/* Subheadline */}
            <p className="text-lg md:text-xl text-white/70 max-w-2xl mx-auto mb-10 opacity-0 leading-relaxed">
              I'm Stephen Annan, a graphic designer passionate about transforming ideas into 
              compelling visual stories through design and branding.
            </p>

            {/* CTA Buttons */}
            <div className="flex flex-col sm:flex-row gap-4 justify-center opacity-0">
              <Button asChild variant="hero" size="xl">
                <Link to="/portfolio">
                  View Portfolio
                  <ArrowRight className="ml-2 h-5 w-5" />
                </Link>
              </Button>
              <Button asChild variant="heroOutline" size="xl">
                <Link to="/contact">Contact Me</Link>
              </Button>
            </div>
          </div>

          {/* Stats */}
          <div className="mt-20 grid grid-cols-3 gap-8 max-w-2xl mx-auto animate-fade-in" style={{ animationDelay: "0.8s" }}>
            {stats.map((stat) => (
              <div key={stat.label} className="text-center">
                <div className="text-3xl md:text-4xl font-bold text-white mb-1">
                  {stat.value}
                </div>
                <div className="text-sm text-white/60">{stat.label}</div>
              </div>
            ))}
          </div>
        </div>

        {/* Scroll Indicator */}
        <div className="absolute bottom-8 left-1/2 -translate-x-1/2 animate-float">
          <div className="w-6 h-10 border-2 border-white/30 rounded-full flex items-start justify-center p-1">
            <div className="w-1.5 h-3 bg-white/50 rounded-full animate-pulse" />
          </div>
        </div>
      </section>

      {/* Featured Work Section */}
      <section className="section-padding bg-background">
        <div className="container-custom">
          {/* Section Header */}
          <div className="flex flex-col md:flex-row md:items-end justify-between gap-6 mb-16">
            <div>
              <p className="text-accent font-medium mb-2">Featured Work</p>
              <h2 className="text-3xl md:text-4xl lg:text-5xl font-bold text-foreground">
                Recent Projects
              </h2>
            </div>
            <Button asChild variant="outline" size="lg">
              <Link to="/portfolio">
                View All Work
                <ArrowRight className="ml-2 h-4 w-4" />
              </Link>
            </Button>
          </div>

          {/* Work Grid */}
          <div className="grid md:grid-cols-3 gap-6">
            {featuredWork.map((work, index) => (
              <Link
                key={work.id}
                to="/portfolio"
                className="group portfolio-item relative aspect-square rounded-2xl overflow-hidden card-hover"
                style={{ animationDelay: `${index * 0.1}s` }}
              >
                <img
                  src={work.image}
                  alt={work.title}
                  className="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
                />
                <div className="portfolio-overlay rounded-2xl">
                  <div className="text-center text-white">
                    <p className="text-sm text-accent mb-2">{work.category}</p>
                    <h3 className="text-xl font-bold">{work.title}</h3>
                  </div>
                </div>
              </Link>
            ))}
          </div>
        </div>
      </section>

      {/* CTA Section */}
      <section className="section-padding hero-gradient">
        <div className="container-custom text-center">
          <h2 className="text-3xl md:text-4xl lg:text-5xl font-bold text-white mb-6">
            Let's Create Something
            <br />
            <span className="text-gradient">Amazing Together</span>
          </h2>
          <p className="text-white/70 max-w-xl mx-auto mb-10 text-lg">
            Have a project in mind? I'd love to hear about it. Let's discuss how 
            we can bring your vision to life.
          </p>
          <Button asChild variant="hero" size="xl">
            <Link to="/contact">
              Start a Project
              <ArrowRight className="ml-2 h-5 w-5" />
            </Link>
          </Button>
        </div>
      </section>
    </Layout>
  );
};

export default Index;
