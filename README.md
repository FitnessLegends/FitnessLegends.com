import { motion } from 'motion/react';
import { 
  CheckCircle2, 
  Clock, 
  Home, 
  MapPin, 
  ShieldCheck, 
  Star, 
  Target, 
  TrendingUp, 
  Users, 
  Zap,
  ChevronRight,
  ArrowRight,
  Calendar
} from 'lucide-react';

const FadeIn = ({ children, delay = 0 }: { children: React.ReactNode, delay?: number }) => (
  <motion.div
    initial={{ opacity: 0, y: 20 }}
    whileInView={{ opacity: 1, y: 0 }}
    viewport={{ once: true, margin: "-100px" }}
    transition={{ duration: 0.6, delay }}
  >
    {children}
  </motion.div>
);

const BOOKING_LINK = "https://www.picktime.com/9a30edcb-1339-4e7b-bc72-9d3dc88904f4";

export default function App() {
  return (
    <div className="min-h-screen bg-zinc-50 font-sans text-zinc-900 selection:bg-orange-500/30 selection:text-orange-900 pb-20 md:pb-0">
      {/* NAVIGATION */}
      <nav className="sticky top-0 z-50 bg-zinc-950/95 backdrop-blur-md border-b border-zinc-800">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between items-center h-20">
            <div className="flex items-center gap-2">
              <img src="/logo.png" alt="Fitness Legends" className="h-10 md:h-12 w-auto object-contain" />
            </div>
            <div className="hidden md:flex items-center gap-8 font-medium text-sm text-zinc-300">
              <a href="#services" className="hover:text-orange-500 transition-colors">Services</a>
              <a href="#how-it-works" className="hover:text-orange-500 transition-colors">How It Works</a>
              <a href="#results" className="hover:text-orange-500 transition-colors">Results</a>
              <a href="#faq" className="hover:text-orange-500 transition-colors">FAQ</a>
            </div>
            <div className="hidden md:block">
              <a 
                href={BOOKING_LINK}
                target="_blank"
                rel="noopener noreferrer"
                className="inline-flex items-center justify-center px-6 py-2.5 border border-transparent text-sm font-bold rounded-full text-zinc-950 bg-gradient-to-r from-orange-500 to-amber-500 hover:from-orange-400 hover:to-amber-400 transition-all shadow-sm hover:shadow-orange-500/25"
              >
                Book Consultation
              </a>
            </div>
          </div>
        </div>
      </nav>

      {/* MOBILE STICKY CTA */}
      <div className="md:hidden fixed bottom-0 left-0 right-0 p-4 bg-zinc-950/95 backdrop-blur-md border-t border-zinc-800 z-50">
        <a 
          href={BOOKING_LINK}
          target="_blank"
          rel="noopener noreferrer"
          className="flex items-center justify-center w-full px-6 py-3.5 text-base font-bold rounded-full text-zinc-950 bg-gradient-to-r from-orange-500 to-amber-500 shadow-lg shadow-orange-500/20"
        >
          <Calendar className="w-5 h-5 mr-2" />
          Book Your Session Now
        </a>
      </div>

      {/* 1. HERO SECTION */}
      <section className="relative pt-20 pb-32 lg:pt-32 lg:pb-40 overflow-hidden bg-zinc-950 text-white">
        <div className="absolute inset-0 opacity-20 bg-[url('https://images.unsplash.com/photo-1571019614242-c5c5dee9f50b?q=80&w=2070&auto=format&fit=crop')] bg-cover bg-center mix-blend-overlay"></div>
        <div className="absolute inset-0 bg-gradient-to-t from-zinc-950 via-zinc-950/80 to-transparent"></div>
        
        <div className="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
          <FadeIn>
            <span className="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-orange-500/10 text-orange-400 text-sm font-semibold tracking-wide uppercase mb-6 border border-orange-500/20">
              <MapPin className="w-4 h-4" /> South East Queensland
            </span>
            <h1 className="text-5xl md:text-7xl font-extrabold tracking-tight mb-6 leading-tight">
              Skip the Commute. <br className="hidden md:block" />
              <span className="text-transparent bg-clip-text bg-gradient-to-r from-orange-500 to-amber-400">Get the Results.</span>
            </h1>
            <p className="mt-4 text-xl md:text-2xl text-zinc-400 max-w-3xl mx-auto font-light leading-relaxed mb-10">
              Expert mobile personal training designed for beginners and busy professionals. We bring the gym to you for sustainable fat loss and strength—without the intimidation.
            </p>
            <div className="flex flex-col sm:flex-row gap-4 justify-center items-center">
              <a 
                href={BOOKING_LINK}
                target="_blank"
                rel="noopener noreferrer"
                className="w-full sm:w-auto inline-flex items-center justify-center px-8 py-4 text-lg font-bold rounded-full text-zinc-950 bg-gradient-to-r from-orange-500 to-amber-500 hover:from-orange-400 hover:to-amber-400 transition-all shadow-lg hover:shadow-orange-500/25 hover:-translate-y-0.5"
              >
                Book Your Free Consultation
                <ArrowRight className="ml-2 w-5 h-5" />
              </a>
              <a href="#how-it-works" className="w-full sm:w-auto inline-flex items-center justify-center px-8 py-4 text-lg font-semibold rounded-full text-white bg-white/5 hover:bg-white/10 border border-white/10 transition-all backdrop-blur-sm">
                See How It Works
              </a>
            </div>
          </FadeIn>
        </div>
      </section>

      {/* 2. PROBLEM SECTION */}
      <section className="py-24 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="grid lg:grid-cols-2 gap-16 items-center">
            <FadeIn>
              <h2 className="text-3xl md:text-4xl font-bold text-zinc-900 mb-6">
                Fitness shouldn't feel like another chore.
              </h2>
              <p className="text-lg text-zinc-600 mb-8 leading-relaxed">
                You know you need to exercise, but the traditional gym model is failing you. You don't need more guilt. You need a system that fits your actual life.
              </p>
              <ul className="space-y-6">
                {[
                  "You're short on time and can't justify a 40-minute round trip to a crowded gym.",
                  "The gym environment feels intimidating, judgmental, and overwhelming.",
                  "You lack a structured plan, leaving you guessing what to do next.",
                  "Your motivation spikes on Monday and disappears by Wednesday."
                ].map((item, i) => (
                  <li key={i} className="flex items-start gap-4">
                    <div className="flex-shrink-0 w-6 h-6 rounded-full bg-orange-100 flex items-center justify-center mt-1">
                      <div className="w-2 h-2 rounded-full bg-orange-500"></div>
                    </div>
                    <span className="text-zinc-700 text-lg">{item}</span>
                  </li>
                ))}
              </ul>
            </FadeIn>
            <FadeIn delay={0.2}>
              <div className="relative rounded-2xl overflow-hidden shadow-2xl">
                <img 
                  src="https://images.unsplash.com/photo-1517836357463-d25dfeac3438?q=80&w=2070&auto=format&fit=crop" 
                  alt="Frustrated person thinking about fitness" 
                  className="w-full h-[500px] object-cover grayscale-[20%]"
                  referrerPolicy="no-referrer"
                />
                <div className="absolute inset-0 bg-gradient-to-t from-zinc-900/60 to-transparent"></div>
              </div>
            </FadeIn>
          </div>
        </div>
      </section>

      {/* 3. SOLUTION SECTION */}
      <section className="py-24 bg-zinc-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
          <FadeIn>
            <h2 className="text-3xl md:text-5xl font-bold text-zinc-900 mb-6">
              Enter Fitness Legends. <br className="hidden md:block" />
              <span className="text-transparent bg-clip-text bg-gradient-to-r from-orange-500 to-amber-500">Your At-Home Fitness Solution.</span>
            </h2>
            <p className="text-xl text-zinc-600 max-w-3xl mx-auto mb-16">
              We eliminate the friction between you and your goals. As a premier mobile personal trainer in South East Queensland, we deliver expert coaching directly to your living room, backyard, or local park.
            </p>
          </FadeIn>

          <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
            {[
              { icon: Home, title: "Zero Travel Time", desc: "We come to you. Reclaim hours of your week." },
              { icon: ShieldCheck, title: "Complete Privacy", desc: "No onlookers, no waiting for equipment." },
              { icon: Target, title: "100% Personalised", desc: "Built for your body, goals, and schedule." },
              { icon: CheckCircle2, title: "Unwavering Accountability", desc: "We show up, so you show up." }
            ].map((feature, i) => (
              <FadeIn key={i} delay={i * 0.1}>
                <div className="bg-white p-8 rounded-2xl shadow-sm border border-zinc-200 h-full hover:shadow-md transition-shadow hover:border-orange-200">
                  <div className="w-14 h-14 bg-orange-50 rounded-xl flex items-center justify-center mb-6 mx-auto">
                    <feature.icon className="w-7 h-7 text-orange-500" />
                  </div>
                  <h3 className="text-xl font-bold text-zinc-900 mb-3">{feature.title}</h3>
                  <p className="text-zinc-600">{feature.desc}</p>
                </div>
              </FadeIn>
            ))}
          </div>
        </div>
      </section>

      {/* 4. SERVICES SECTION */}
      <section id="services" className="py-24 bg-zinc-950 text-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <FadeIn>
            <div className="text-center mb-16">
              <h2 className="text-3xl md:text-5xl font-bold mb-6">Tailored Training for Real People.</h2>
              <p className="text-xl text-zinc-400 max-w-2xl mx-auto">No cookie-cutter programs. Just effective, science-backed training designed for your specific needs.</p>
            </div>
          </FadeIn>

          <div className="grid md:grid-cols-2 gap-6">
            {[
              {
                title: "1-on-1 Mobile Personal Training",
                what: "Private, highly focused sessions at your home.",
                who: "Busy professionals and beginners wanting maximum accountability.",
                outcome: "Faster results, perfect form, and a routine you actually enjoy."
              },
              {
                title: "Beginner Foundations Program",
                what: "A step-by-step introduction to movement and strength.",
                who: "Anyone who hasn't worked out in years (or ever).",
                outcome: "Build confidence, learn proper technique, and establish a baseline safely."
              },
              {
                title: "Small Group Training",
                what: "Train with 2-3 friends or family members.",
                who: "Those who want shared motivation and a cost-effective option.",
                outcome: "Fun, competitive workouts that build strength and community."
              },
              {
                title: "Strength & Conditioning",
                what: "Progressive resistance training using minimal equipment.",
                who: "Clients looking to tone up, build lean muscle, and increase energy.",
                outcome: "A stronger, more resilient body capable of handling daily life with ease."
              }
            ].map((service, i) => (
              <FadeIn key={i} delay={i * 0.1}>
                <div className="bg-zinc-900/50 border border-zinc-800 p-8 rounded-2xl h-full hover:bg-zinc-900 transition-colors hover:border-orange-500/30">
                  <h3 className="text-2xl font-bold text-orange-400 mb-6">{service.title}</h3>
                  <div className="space-y-4">
                    <div>
                      <span className="text-xs font-bold tracking-wider text-zinc-500 uppercase block mb-1">What it is</span>
                      <p className="text-zinc-300">{service.what}</p>
                    </div>
                    <div>
                      <span className="text-xs font-bold tracking-wider text-zinc-500 uppercase block mb-1">Who it's for</span>
                      <p className="text-zinc-300">{service.who}</p>
                    </div>
                    <div>
                      <span className="text-xs font-bold tracking-wider text-zinc-500 uppercase block mb-1">Outcome</span>
                      <p className="text-white font-medium">{service.outcome}</p>
                    </div>
                  </div>
                </div>
              </FadeIn>
            ))}
          </div>
        </div>
      </section>

      {/* 5. HOW IT WORKS */}
      <section id="how-it-works" className="py-24 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <FadeIn>
            <div className="text-center mb-16">
              <h2 className="text-3xl md:text-5xl font-bold text-zinc-900 mb-6">Your Path to Results in 3 Simple Steps.</h2>
              <p className="text-xl text-zinc-600 max-w-2xl mx-auto">We've removed all the guesswork. Getting started is easier than driving to the gym.</p>
            </div>
          </FadeIn>

          <div className="grid md:grid-cols-3 gap-12 relative">
            <div className="hidden md:block absolute top-12 left-[15%] right-[15%] h-0.5 bg-zinc-100"></div>
            
            {[
              {
                step: "01",
                title: "Book a Consultation",
                desc: "Choose a time that works for you directly in our calendar for a quick, no-pressure chat."
              },
              {
                step: "02",
                title: "Get Your Custom Plan",
                desc: "We design a sustainable fitness and nutrition strategy tailored specifically to you."
              },
              {
                step: "03",
                title: "Train at Home",
                desc: "We arrive with the equipment and the expertise. You just show up ready to work."
              }
            ].map((item, i) => (
              <FadeIn key={i} delay={i * 0.2}>
                <div className="relative text-center z-10">
                  <div className="w-24 h-24 mx-auto bg-white border-4 border-zinc-50 rounded-full flex items-center justify-center shadow-xl mb-6">
                    <span className="text-3xl font-black text-transparent bg-clip-text bg-gradient-to-br from-orange-500 to-amber-500">{item.step}</span>
                  </div>
                  <h3 className="text-2xl font-bold text-zinc-900 mb-4">{item.title}</h3>
                  <p className="text-zinc-600 leading-relaxed">{item.desc}</p>
                </div>
              </FadeIn>
            ))}
          </div>
          
          <div className="mt-16 text-center hidden md:block">
            <a 
              href={BOOKING_LINK}
              target="_blank"
              rel="noopener noreferrer"
              className="inline-flex items-center justify-center px-8 py-4 text-lg font-bold rounded-full text-zinc-950 bg-gradient-to-r from-orange-500 to-amber-500 hover:from-orange-400 hover:to-amber-400 transition-colors shadow-lg shadow-orange-500/20 hover:-translate-y-0.5"
            >
              Start Step 01 Now
            </a>
          </div>
        </div>
      </section>

      {/* 6. RESULTS / BENEFITS SECTION */}
      <section id="results" className="py-24 bg-zinc-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="grid lg:grid-cols-2 gap-16 items-center">
            <FadeIn>
              <div className="relative rounded-2xl overflow-hidden shadow-2xl">
                <img 
                  src="https://images.unsplash.com/photo-1594381898411-846e7d193883?q=80&w=1974&auto=format&fit=crop" 
                  alt="Healthy active lifestyle" 
                  className="w-full h-[600px] object-cover"
                  referrerPolicy="no-referrer"
                />
                <div className="absolute inset-0 bg-orange-500/10 mix-blend-multiply"></div>
              </div>
            </FadeIn>
            <FadeIn delay={0.2}>
              <h2 className="text-3xl md:text-5xl font-bold text-zinc-900 mb-6">
                What Happens When You Commit.
              </h2>
              <p className="text-lg text-zinc-600 mb-10 leading-relaxed">
                We don't care about how much you can bench press. We focus on outcomes that actually matter to your daily life.
              </p>
              <ul className="space-y-6">
                {[
                  { icon: TrendingUp, text: "Sustainable fat loss without extreme diets." },
                  { icon: Zap, text: "Functional strength to carry groceries, play with kids, and move without pain." },
                  { icon: Star, text: "Unshakable confidence in your own skin." },
                  { icon: Clock, text: "Sustained energy levels throughout the workday." },
                  { icon: ShieldCheck, text: "A permanent lifestyle change, not a 30-day quick fix." }
                ].map((item, i) => (
                  <li key={i} className="flex items-center gap-4 bg-white p-4 rounded-xl shadow-sm border border-zinc-100">
                    <div className="flex-shrink-0 w-10 h-10 rounded-full bg-orange-50 flex items-center justify-center">
                      <item.icon className="w-5 h-5 text-orange-500" />
                    </div>
                    <span className="text-zinc-800 font-medium text-lg">{item.text}</span>
                  </li>
                ))}
              </ul>
            </FadeIn>
          </div>
        </div>
      </section>

      {/* 7. SOCIAL PROOF SECTION */}
      <section className="py-24 bg-zinc-950 text-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <FadeIn>
            <div className="text-center mb-16">
              <h2 className="text-3xl md:text-5xl font-bold mb-6">Real People. Real Results.</h2>
              <p className="text-xl text-zinc-400 max-w-2xl mx-auto">Don't just take our word for it. See what our clients have achieved from the comfort of their own homes.</p>
            </div>
          </FadeIn>

          <div className="grid md:grid-cols-3 gap-8">
            {[
              {
                quote: "I was terrified of gyms. Having a trainer come to my house changed everything. I've lost 8kg and finally feel strong.",
                name: "Sarah M.",
                location: "Brisbane",
                tag: "Beginner Success"
              },
              {
                quote: "Between work and kids, I had zero time. Fitness Legends removed every excuse. The workouts are challenging but totally doable.",
                name: "Emma T.",
                location: "Gold Coast",
                tag: "Busy Professional"
              },
              {
                quote: "I started as a complete beginner. My trainer was patient, professional, and pushed me just the right amount. Highly recommend.",
                name: "Jessica L.",
                location: "Logan",
                tag: "Confidence Built"
              }
            ].map((testimonial, i) => (
              <FadeIn key={i} delay={i * 0.1}>
                <div className="bg-zinc-900 p-8 rounded-2xl relative h-full flex flex-col border border-zinc-800">
                  <div className="flex text-orange-400 mb-6">
                    {[...Array(5)].map((_, j) => <Star key={j} className="w-5 h-5 fill-current" />)}
                  </div>
                  <p className="text-lg text-zinc-300 italic mb-8 flex-grow">"{testimonial.quote}"</p>
                  <div>
                    <p className="font-bold text-white">{testimonial.name}</p>
                    <p className="text-sm text-zinc-400">{testimonial.location}</p>
                    <span className="inline-block mt-3 text-xs font-semibold px-2.5 py-1 rounded-full bg-zinc-800 text-zinc-300 border border-zinc-700">
                      {testimonial.tag}
                    </span>
                  </div>
                </div>
              </FadeIn>
            ))}
          </div>
        </div>
      </section>

      {/* 8. ABOUT SECTION */}
      <section className="py-24 bg-white">
        <div className="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
          <FadeIn>
            <Users className="w-16 h-16 text-orange-500 mx-auto mb-8" />
            <h2 className="text-3xl md:text-5xl font-bold text-zinc-900 mb-8">Expert Coaching, Zero Judgment.</h2>
            <div className="text-xl text-zinc-600 space-y-6 leading-relaxed">
              <p>
                At Fitness Legends, we believe fitness should adapt to your life, not the other way around. We are professional, results-driven coaches dedicated to helping beginners and busy professionals build strength and lose fat safely.
              </p>
              <p>
                We don't do drill-sergeant yelling or impossible diets. We provide structured, sustainable guidance that gets you from where you are to where you want to be.
              </p>
            </div>
          </FadeIn>
        </div>
      </section>

      {/* 9. OBJECTION HANDLING SECTION */}
      <section className="py-24 bg-zinc-50 border-y border-zinc-200">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <FadeIn>
            <div className="text-center mb-16">
              <h2 className="text-3xl md:text-5xl font-bold text-zinc-900 mb-6">Still Unsure? Let's Clear That Up.</h2>
            </div>
          </FadeIn>

          <div className="grid md:grid-cols-2 gap-8 max-w-5xl mx-auto">
            {[
              {
                q: "I'm too unfit to start.",
                a: "Our programs are designed specifically for beginners. We meet you exactly where you are and progress at your pace."
              },
              {
                q: "I don't have time.",
                a: "That's exactly why we come to you. A highly effective workout takes just 45 minutes, zero commute required."
              },
              {
                q: "I've failed before.",
                a: "You didn't fail; the generic plans failed you. We provide the accountability and personalization needed to make it stick."
              },
              {
                q: "Training at home won't work.",
                a: "You don't need heavy machines to get results. We bring specialized equipment and use proven methods to deliver gym-quality workouts anywhere."
              }
            ].map((item, i) => (
              <FadeIn key={i} delay={i * 0.1}>
                <div className="bg-white p-8 rounded-2xl shadow-sm border border-zinc-100">
                  <h3 className="text-xl font-bold text-zinc-900 mb-3 flex items-center gap-3">
                    <span className="text-orange-500 font-black text-2xl">"</span>
                    {item.q}
                    <span className="text-orange-500 font-black text-2xl">"</span>
                  </h3>
                  <p className="text-zinc-600 leading-relaxed">{item.a}</p>
                </div>
              </FadeIn>
            ))}
          </div>
        </div>
      </section>

      {/* 11. FAQ SECTION */}
      <section id="faq" className="py-24 bg-white">
        <div className="max-w-3xl mx-auto px-4 sm:px-6 lg:px-8">
          <FadeIn>
            <h2 className="text-3xl md:text-5xl font-bold text-zinc-900 mb-12 text-center">Frequently Asked Questions</h2>
            <div className="space-y-8">
              {[
                {
                  q: "How much does it cost?",
                  a: "Think of this as an investment in your long-term health. Packages vary based on frequency. Book a consultation for a customized quote."
                },
                {
                  q: "Do I need my own gear?",
                  a: "Not at all. We bring all necessary equipment, from dumbbells to resistance bands. Just provide a small space to move."
                },
                {
                  q: "Where do you train?",
                  a: "We service the greater South East Queensland area, including Brisbane, Gold Coast, and surrounding suburbs."
                },
                {
                  q: "How long are the sessions?",
                  a: "Sessions are typically 45 to 60 minutes, optimized for maximum results without wasting your day."
                },
                {
                  q: "What is your cancellation policy?",
                  a: "We require 24 hours' notice for cancellations to respect our trainers' schedules and keep you accountable."
                }
              ].map((faq, i) => (
                <div key={i} className="border-b border-zinc-200 pb-8 last:border-0">
                  <h3 className="text-xl font-bold text-zinc-900 mb-3">{faq.q}</h3>
                  <p className="text-zinc-600">{faq.a}</p>
                </div>
              ))}
            </div>
          </FadeIn>
        </div>
      </section>

      {/* 10. CALL TO ACTION SECTION */}
      <section id="contact" className="py-24 bg-zinc-950 text-white relative overflow-hidden">
        <div className="absolute inset-0 opacity-20 bg-[url('https://images.unsplash.com/photo-1534438327276-14e5300c3a48?q=80&w=2070&auto=format&fit=crop')] bg-cover bg-center mix-blend-overlay"></div>
        <div className="absolute inset-0 bg-gradient-to-t from-zinc-950 via-zinc-950/80 to-transparent"></div>
        
        <div className="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 text-center relative z-10">
          <FadeIn>
            <h2 className="text-4xl md:text-6xl font-extrabold mb-6 tracking-tight">Stop Waiting for the "Perfect Time".</h2>
            <p className="text-xl md:text-2xl text-zinc-300 mb-12 max-w-2xl mx-auto font-light">
              The perfect time is right now. Reclaim your health, build your confidence, and experience the ultimate convenience of at-home personal training.
            </p>
            
            <div className="bg-zinc-900/80 backdrop-blur-md p-8 md:p-12 rounded-3xl border border-zinc-800 shadow-2xl">
              <div className="grid md:grid-cols-2 gap-12 items-center">
                <div className="text-left">
                  <h3 className="text-3xl font-bold mb-4">Ready to start?</h3>
                  <p className="text-zinc-400 mb-8 text-lg">
                    Skip the back-and-forth emails. Choose a time that works for you directly in our calendar.
                  </p>
                  
                  <a 
                    href={BOOKING_LINK}
                    target="_blank"
                    rel="noopener noreferrer"
                    className="w-full py-5 text-lg font-bold rounded-xl text-zinc-950 bg-gradient-to-r from-orange-500 to-amber-500 hover:from-orange-400 hover:to-amber-400 transition-all shadow-lg shadow-orange-500/20 flex items-center justify-center gap-3 hover:-translate-y-1"
                  >
                    <Calendar className="w-6 h-6" />
                    Open Booking Calendar
                  </a>
                  <p className="text-sm text-zinc-500 text-center mt-4">No commitment required. We'll chat about your goals.</p>
                </div>
                
                <div className="flex flex-col items-center justify-center border-t md:border-t-0 md:border-l border-zinc-800 pt-8 md:pt-0 md:pl-12">
                  <h3 className="text-xl font-bold mb-6 text-center text-zinc-300">Or Scan to Book on Mobile</h3>
                  <div className="bg-white p-4 rounded-2xl shadow-2xl transform transition-transform hover:scale-105 border-4 border-zinc-800">
                    <img src="/qr_code.png" alt="Scan to Book" className="w-48 h-48 object-contain" />
                  </div>
                </div>
              </div>
            </div>
          </FadeIn>
        </div>
      </section>

      {/* FOOTER */}
      <footer className="bg-zinc-950 text-zinc-500 py-12 border-t border-zinc-900">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 grid md:grid-cols-3 gap-8 items-center">
          <div>
            <div className="flex items-center gap-2 mb-6">
              <img src="/logo.png" alt="Fitness Legends" className="h-10 w-auto object-contain opacity-80 hover:opacity-100 transition-opacity" />
            </div>
            <p className="text-sm">Premium mobile personal training in South East Queensland. We bring the gym to you.</p>
          </div>
          <div className="text-sm space-y-2 md:text-center">
            <p>Mobile personal trainer Brisbane</p>
            <p>At home personal training</p>
            <p>Personal trainer South East Queensland</p>
            <p>Beginner fitness coaching</p>
          </div>
          <div className="md:text-right text-sm">
            <p>&copy; {new Date().getFullYear()} Fitness Legends. All rights reserved.</p>
          </div>
        </div>
      </footer>
    </div>
  );
}
