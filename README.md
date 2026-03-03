# Ancestor 
"use client";

import { useState, useEffect } from "react";
import { motion } from "framer-motion";

export default function Home() {

  const [loading, setLoading] = useState(true);

  useEffect(() => {
    setTimeout(() => {
      setLoading(false);
    }, 2500);
  }, []);

  if (loading) {
    return (
      <div style={loaderStyle}>
        <h1 style={{color:"#d4af37"}}>Lamar Creative Studio</h1>
        <p>Loading Premium Experience...</p>
      </div>
    );
  }

  return (
    <main style={mainStyle}>
      
      {/* HERO */}
      <section style={heroStyle}>
        <motion.div
          initial={{ opacity: 0, y: 40 }}
          whileInView={{ opacity: 1, y: 0 }}
          transition={{ duration: 1 }}
        >
          <h1 style={{ fontSize: "50px", color: "#d4af37" }}>
            Lamar Creative Studio
          </h1>
          <p>Digital Brand Strategist | Cinematographer | Growth Expert</p>
        </motion.div>
      </section>

      {/* ABOUT */}
      <Section title="About Lamar">
        I am Adebayo Oluwamuyiwa Ayomide (Lamar), a premium Digital Brand
        Strategist helping businesses scale through positioning, elite visuals
        and conversion-driven strategy.
      </Section>

      {/* SERVICES */}
      <Section title="Premium Services">
        <ul>
          <li>High-Converting Graphic Design</li>
          <li>TikTok Branding & Growth</li>
          <li>Professional CV & LinkedIn Optimization</li>
          <li>Cinematography & Video Editing</li>
          <li>Full Social Media Management</li>
        </ul>
      </Section>

      {/* PRICING */}
      <Section title="Premium Packages">
        <div style={pricingContainer}>
          <PricingCard
            title="Starter Brand Package"
            price="₦100,000"
            items={["Brand Strategy", "Flyer Design", "Profile Optimization"]}
          />
          <PricingCard
            title="Growth Domination"
            price="₦250,000"
            items={["Content Strategy", "Video Production", "Social Management"]}
          />
          <PricingCard
            title="Elite Corporate Package"
            price="₦500,000+"
            items={["Full Brand Overhaul", "Cinematography", "Premium Campaign"]}
          />
        </div>
      </Section>

      {/* BOOKING FORM */}
      <Section title="Book Consultation">
        <form style={formStyle}>
          <input placeholder="Full Name" required />
          <input placeholder="Email" required />
          <textarea placeholder="Tell us about your project" required />
          <button type="submit">Submit</button>
        </form>
      </Section>

      {/* SOCIALS */}
      <Section title="Connect With Lamar">
        <p>TikTok: @afobaje_13</p>
        <p>Instagram: @afobaje_13</p>
        <p>Facebook: Lamar scopic</p>
        <p>X: @afobaje_13</p>
      </Section>

      <footer style={{ textAlign: "center", padding: "40px", color: "#777" }}>
        © 2026 Lamar Creative Studio
      </footer>

    </main>
  );
}

function Section({ title, children }) {
  return (
    <motion.section
      style={sectionStyle}
      initial={{ opacity: 0, y: 50 }}
      whileInView={{ opacity: 1, y: 0 }}
      transition={{ duration: 0.8 }}
    >
      <h2 style={{ color: "#d4af37" }}>{title}</h2>
      <div>{children}</div>
    </motion.section>
  );
}

function PricingCard({ title, price, items }) {
  return (
    <motion.div
      style={cardStyle}
      whileHover={{ scale: 1.05 }}
    >
      <h3>{title}</h3>
      <h2 style={{ color: "#d4af37" }}>{price}</h2>
      <ul>
        {items.map((item, index) => (
          <li key={index}>{item}</li>
        ))}
      </ul>
    </motion.div>
  );
}

/* STYLES */

const mainStyle = {
  background: "#0b0b0b",
  color: "white",
  fontFamily: "sans-serif"
};

const heroStyle = {
  height: "90vh",
  display: "flex",
  alignItems: "center",
  justifyContent: "center",
  textAlign: "center"
};

const sectionStyle = {
  padding: "100px 10%"
};

const cardStyle = {
  background: "#111",
  padding: "30px",
  borderRadius: "20px",
  border: "1px solid #d4af37",
  width: "300px"
};

const pricingContainer = {
  display: "flex",
  gap: "30px",
  flexWrap: "wrap"
};

const formStyle = {
  display: "flex",
  flexDirection: "column",
  gap: "15px",
  maxWidth: "400px"
};

const loaderStyle = {
  height: "100vh",
  display: "flex",
  flexDirection: "column",
  justifyContent: "center",
  alignItems: "center",
  background: "#000",
  color: "white"
};
