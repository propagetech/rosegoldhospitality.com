You are a naming assistant. Given a list of file paths and minimal context from a static website, suggest a new filename (basename only, same extension) for each file. Rules:
- Lowercase, kebab-case, no spaces. SEO-friendly and human-readable.
- For HTML: use page purpose (e.g. about-us.html, contact.html). Keep index.html as index.html.
- For CSS/JS: use purpose (e.g. main-styles.css, analytics.js).
- For images: use content (e.g. logo-infygate.webp, hero-banner.webp). Use alt/title when provided.
- Return a JSON object: keys = exact original path strings, values = new basename only (e.g. "main.css"). Preserve extension.
- Do not change path prefix (e.g. css/ stays css/ by returning "name.css" not "css/name.css").

Files and context:
[
  {
    "path": "404.html",
    "context": {
      "title": "",
      "first_heading": "404"
    }
  },
  {
    "path": "ROI.html",
    "context": {
      "title": "Hospitality Consultants in India, Hotel Consulting Firm",
      "first_heading": "EXPERT HOTEL AND HOSPITALITY CONSULTANTS IN INDIA"
    }
  },
  {
    "path": "Thank-You-PPC.html",
    "context": {
      "title": "Thank You!",
      "first_heading": "DISCUSS YOUR HOTEL PROJECT."
    }
  },
  {
    "path": "about.html",
    "context": {
      "title": "Hotel Consultants in Delhi, Hospitality Management Company in India",
      "first_heading": "HOSPITALITY AND HOTEL CONSULTANTS IN DELHI"
    }
  },
  {
    "path": "blog.html",
    "context": {
      "title": "Blog",
      "first_heading": "BLOG"
    }
  },
  {
    "path": "blog_5-things-you-must-know-about-the-hotel-development-process.html",
    "context": {
      "title": "5 Things You Must Know About the Hotel Development Process",
      "first_heading": "5 Things You Must Know About the Hotel Development Process"
    }
  },
  {
    "path": "blog_6-points-to-build-a-solid-hotel-marketing-plan.html",
    "context": {
      "title": "6 Points to Build a Solid Hotel Marketing Plan",
      "first_heading": "6 Points to Build a Solid Hotel Marketing Plan"
    }
  },
  {
    "path": "blog_a-hotel-owner-s-guide-to-evolving-domestic-travel-in-india.html",
    "context": {
      "title": "A Hotel Owner\u2019s Guide To Evolving Domestic Travel In India",
      "first_heading": "A Hotel Owner\u2019s Guide To Evolving Domestic Travel In India"
    }
  },
  {
    "path": "blog_how-quality-control-in-hotel-industry-impacts-guest-satisfaction.html",
    "context": {
      "title": "How Quality Control In Hotel Industry Impacts Guest Satisfaction",
      "first_heading": "How Quality Control In Hotel Industry Impacts Guest Satisfaction"
    }
  },
  {
    "path": "blog_how-to-improve-hotel-operations-to-reduce-operating-costs.html",
    "context": {
      "title": "How to Improve Hotel Operations to Reduce Operating Costs",
      "first_heading": "How to Improve Hotel Operations to Reduce Operating Costs"
    }
  },
  {
    "path": "blog_key-influencing-factors-of-adr--occupancy-rate-and-revpar.html",
    "context": {
      "title": "Key Influencing Factors of ADR, Occupancy Rate and RevPAR",
      "first_heading": "Key Influencing Factors of ADR, Occupancy Rate and RevPAR"
    }
  },
  {
    "path": "blog_the-only-hotel-development-strategy-guide-you-will-ever-need.html",
    "context": {
      "title": "The Only Hotel Development Strategy Guide You Will Ever Need",
      "first_heading": "The Only Hotel Development Strategy Guide You Will Ever Need"
    }
  },
  {
    "path": "blog_what-to-expect-from-a-hospitality-consultant-company-in-india.html",
    "context": {
      "title": "What to Expect from a Hospitality Consultant Company in India",
      "first_heading": "What to Expect from a Hospitality Consultant Company in India"
    }
  },
  {
    "path": "careers.html",
    "context": {
      "title": "CAREERS",
      "first_heading": "CAREERS"
    }
  },
  {
    "path": "club-design-and-managment.html",
    "context": {
      "title": "Hotel Asset Management Company, Hotel Property Management Company",
      "first_heading": "CLUB DESIGN AND MANAGEMENT"
    }
  },
  {
    "path": "contact-us.html",
    "context": {
      "title": "CONTACT US",
      "first_heading": "CONTACT US"
    }
  },
  {
    "path": "css/4ba1f7eeea678c518b19a8a229705620.css",
    "context": {
      "path": "css/4ba1f7eeea678c518b19a8a229705620.css"
    }
  },
  {
    "path": "css/559e64bf161e61fa0aca6e864c78191d.css",
    "context": {
      "path": "css/559e64bf161e61fa0aca6e864c78191d.css"
    }
  },
  {
    "path": "css/595cb6ccb56826a802ed411cef875f0e.css",
    "context": {
      "path": "css/595cb6ccb56826a802ed411cef875f0e.css"
    }
  },
  {
    "path": "css/84d4a0216f16f715d9b301db3a8da352.css",
    "context": {
      "path": "css/84d4a0216f16f715d9b301db3a8da352.css"
    }
  },
  {
    "path": "css/99c4e6f40ee9111eea53b6472f3e60f9.css",
    "context": {
      "path": "css/99c4e6f40ee9111eea53b6472f3e60f9.css"
    }
  },
  {
    "path": "css/d09d646f062b67daeff66ff1410b63fc.css",
    "context": {
      "path": "css/d09d646f062b67daeff66ff1410b63fc.css"
    }
  },
  {
    "path": "css/e980cb6b50645ddc9d24377f2fe05d53.css",
    "context": {
      "path": "css/e980cb6b50645ddc9d24377f2fe05d53.css"
    }
  },
  {
    "path": "css/internal-styles.css",
    "context": {
      "path": "css/internal-styles.css"
    }
  },
  {
    "path": "enquiry.html",
    "context": {
      "title": "ENQUIRY",
      "first_heading": "ENQUIRY"
    }
  },
  {
    "path": "hospitality-consultants-m.html",
    "context": {
      "title": "Hotel Management Consultants, Hospitality Management Services",
      "first_heading": "OUR SERVICES"
    }
  },
  {
    "path": "hospitality-consultants.html",
    "context": {
      "title": "Hotel Management Consultants, Hospitality Management Services",
      "first_heading": "HOTEL MANAGEMENT, DEVELOPMENT AND OPERATIONS"
    }
  },
  {
    "path": "hotel-asset-management.html",
    "context": {
      "title": "Hotel Asset Management Company, Hotel Property Management Company",
      "first_heading": "HOTEL ASSET AND PROPERTY MANAGEMENT COMPANY"
    }
  },
  {
    "path": "hotel-brand-development.html",
    "context": {
      "title": "Hotel Brand Development, Hotel Brand Management and Positioning",
      "first_heading": "HOTEL BRAND DEVELOPMENT AND MANAGEMENT"
    }
  },
  {
    "path": "hotel-brand-search.html",
    "context": {
      "title": "Hotel Asset Management Company, Hotel Property Management Company",
      "first_heading": "HOTEL BRAND SEARCH"
    }
  },
  {
    "path": "hotel-development-management.html",
    "context": {
      "title": "Hotel Management Consultants, Hotel Development and Advisory Services",
      "first_heading": "HOTEL MANAGEMENT CONSULTANTS"
    }
  },
  {
    "path": "hotel-feasibility-study.html",
    "context": {
      "title": "Hotel Asset Management Company, Hotel Property Management Company",
      "first_heading": "HOTEL FEASIBILITY STUDY"
    }
  },
  {
    "path": "hotel-financing-.html",
    "context": {
      "title": "Hotel Asset Management Company, Hotel Property Management Company",
      "first_heading": "HOTEL FINANCING"
    }
  },
  {
    "path": "hotel-marketing-sales.html",
    "context": {
      "title": "Hotel Marketing Strategy, Hotel Sales and Marketing Consultants",
      "first_heading": "HOTEL SALES AND MARKETING STRATEGY"
    }
  },
  {
    "path": "hotel-mis.html",
    "context": {
      "title": "Hotel MIS, Hotel Revenue Management Services",
      "first_heading": "HOTEL MIS AND REVENUE MANAGEMENT SERVICES"
    }
  },
  {
    "path": "hotel-operations-management.html",
    "context": {
      "title": "Hotel Operations Management, Hotel Project Management Company",
      "first_heading": "HOTEL OPERATIONS MANAGEMENT COMPANY"
    }
  },
  {
    "path": "hotel-website-guide-thanks.html",
    "context": {
      "title": "Download Your Free Guide!",
      "first_heading": "Embed Code"
    }
  },
  {
    "path": "hotel-website-guide.html",
    "context": {
      "title": "Free Guide: Important Aspects of Designing a Website for a Hotel",
      "first_heading": "The Ultimate Guide to Designing a Website for Your Hotel"
    }
  },
  {
    "path": "imgs/08d503eed72ea2d7b2bf1055319d4bc6.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/0dc3643a23602c5935be118db4aa8091.webp",
    "context": {
      "refs": [
        {
          "alt": "hotel brand search, hotel franchise opportunities, hotel operator",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/17aeadec9d4c5374542828e4157d7968.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1ad99adb03dd8eef645eeb18e969a11b.webp",
    "context": {
      "refs": [
        {
          "alt": "OUR MISSION",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1ec9e866a3316b1bd7acc9f9342e0e07.webp",
    "context": {
      "refs": [
        {
          "alt": "HOTEL TRANSACTION SERVICES",
          "title": ""
        },
        {
          "alt": "hotel",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/208d2357ecc6cacc788fbd3587a5299f.webp",
    "context": {
      "refs": [
        {
          "alt": "OUR VISION",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2730ef372db5bbe8b6df5cac1ad2a061.webp",
    "context": {
      "refs": [
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        },
        {
          "alt": "logo",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2781d9a53a9ff6e832919a41ff27e27f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2e8fb8af96fcf63b1d0d322a8144c625.webp",
    "context": {
      "refs": [
        {
          "alt": "koolinamarriott",
          "title": ""
        },
        {
          "alt": "hospitality consultants in delhi, hotel consultants in delhi, hospitality management companies in in",
          "title": ""
        },
        {
          "alt": "hospitality marketing consultants, hotel marketing strategy, hotel sales and marketing",
          "title": ""
        },
        {
          "alt": "Quality Assessment Evaluation: Conduct the entire Hotel Evaluation based on FLS standards, risk mana",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3109fd8e58cc3c51418060ff590479cb.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/352b57125e0fd76eab7c3be17d47611b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "Manoj Nandkeolyar",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3cc0a70fab108dfdff1378b2af68f8da.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4a8af2f14c29f214ca98dcd3b45a3211.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4d374d54ae70009fa749a9549002bedd.webp",
    "context": {
      "refs": [
        {
          "alt": "PROJECT PLANNING",
          "title": ""
        },
        {
          "alt": "OUR STRATEGIC ADVISORY SERVICES",
          "title": ""
        },
        {
          "alt": "OUR SALES AND MARKETING SERVICES",
          "title": ""
        },
        {
          "alt": "MARKETING AND SALES",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/56cb3b24d4ca3b3b874458f0fac19f88.webp",
    "context": {
      "refs": [
        {
          "alt": "Manoj Nandkeolyar",
          "title": ""
        },
        {
          "alt": "Manoj Nandkeolyar",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5bcaeb74b55be9956e8414e68352489b.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/5d530a0b526902e3b5720fd30331af77.webp",
    "context": {
      "refs": [
        {
          "alt": "a. Implementation of Standard Operating Procedures for all Operational Departments. b. Development o",
          "title": ""
        },
        {
          "alt": "hospitality management services, hotel management and consulting",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6acbd7222461902d5e52bdccb4bb12c4.webp",
    "context": {
      "refs": [
        {
          "alt": "hotel advisory services, hotel development consultants, hotel management consultants",
          "title": ""
        },
        {
          "alt": "OUR STRENGTHS",
          "title": ""
        },
        {
          "alt": "hotel operations management, hotel project management company, hotel management and operations",
          "title": ""
        },
        {
          "alt": "a. Implementation of Standard Operating Procedures for all Operational Departments. b. Development o",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6c064a13f8b02b6299879b11dd4204e8.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/70e925c64d6583106d2bc23fccb9cebf.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/76b25a39e46fe9dbc7c6ddf28533c6c0.webp",
    "context": {
      "refs": [
        {
          "alt": "ml",
          "title": ""
        },
        {
          "alt": "OUR SERVICES",
          "title": ""
        },
        {
          "alt": "BENEFITS OF UTILIZING MIS SERVICES",
          "title": ""
        },
        {
          "alt": "PROFESSIONAL TEAM",
          "title": ""
        },
        {
          "alt": "ml",
          "title": ""
        },
        {
          "alt": "ml",
          "title": ""
        },
        {
          "alt": "BRAND DEVELOPMENT",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/76c3090688fc25aab51d5c3380222bd8.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/770ffd45fbac0503dc41518c5b1e278b.webp",
    "context": {
      "refs": [
        {
          "alt": "The Ultimate Guide to Designing a Website for Your Hotel",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7c7713b8790e0f37d3a4bb120e3576fd.webp",
    "context": {
      "refs": [
        {
          "alt": "PRE-OPENING MANAGEMENT",
          "title": ""
        },
        {
          "alt": "HOTEL ASSET MANAGEMENT SERVICES",
          "title": ""
        },
        {
          "alt": "Our ongoing operations management elements include:",
          "title": ""
        },
        {
          "alt": "BRAND REPRESENTATION\u200b. We assist Hotel Chains that are currently unrepresented in South Asia for the",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8507c750055612cfcc55d273ebb6af99.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/90c6286bca67bfd7e3b586989dacff51.webp",
    "context": {
      "refs": [
        {
          "alt": "hotel asset management company, hotel property management company",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9890655d48b53074412dc9f786518cb6.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9ac75f07d2efcc75bd7d5b782a62bd20.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a93d71e76870e86f87384c7fb4cd19b0.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b0d8a52af9705875479716cc31092feb.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/be79e09dae8892ed08b909dff439f2a0.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cd808c6e2ec8d8786b2943123de3e4db.webp",
    "context": {
      "refs": [
        {
          "alt": "hotel financing, hotel funding sources, loan for hotel business",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d0be37b3276e208ede5fa9cfe774bc1c.webp",
    "context": {
      "refs": [
        {
          "alt": "OUR HOTEL CONSULTING SERVICES INCLUDE",
          "title": ""
        },
        {
          "alt": "COMMITMENT TO VALUE DEVELOPMENT",
          "title": ""
        },
        {
          "alt": "STRONG HOTEL MIS",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d148d206605334d4b28064eddfd1543c.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d4364e8480e15ad3a497b48917796a6a.webp",
    "context": {
      "refs": [
        {
          "alt": "resort management company, resort management consultants, resort management services",
          "title": ""
        },
        {
          "alt": "SMART TEAM",
          "title": ""
        },
        {
          "alt": "MANAGEMENT ADVISORY SERVICES",
          "title": ""
        },
        {
          "alt": "ASSET MANAGEMENT",
          "title": ""
        },
        {
          "alt": "OUR BRANDING TEAM",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e20b45990687863eea316db1cb556e0f.webp",
    "context": {
      "refs": [
        {
          "alt": "TECHNICAL ASSISTANCE",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e563174ad694886b7b80699eea7048b3.webp",
    "context": {
      "refs": [
        {
          "alt": "OUR TEAM",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fd3046050e4d102a5b252de899391481.webp",
    "context": {
      "refs": [
        {
          "alt": "hospitality consultants in india, hotel consulting firm",
          "title": ""
        },
        {
          "alt": "Focus on Total Quality Management and Excellence specially the guest centric areas of rooms, F&B and",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fef856acb4347279222fc5d2f1727814.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "index.html",
    "context": {
      "title": "Hospitality Consulting Services, Hotel Management Company in India",
      "first_heading": "HOTEL MANAGEMENT COMPANY FOR EXPONENTIAL REVENUE GROWTH"
    }
  },
  {
    "path": "js/03b2eaae6007054a68c38e495f894dba.js",
    "context": {
      "path": "js/03b2eaae6007054a68c38e495f894dba.js"
    }
  },
  {
    "path": "js/0a105d712b6a6c836c48dd97d0f0cac1.js",
    "context": {
      "path": "js/0a105d712b6a6c836c48dd97d0f0cac1.js"
    }
  },
  {
    "path": "js/0c46896987137b0016246f6bc2243099.js",
    "context": {
      "path": "js/0c46896987137b0016246f6bc2243099.js"
    }
  },
  {
    "path": "js/165d7b0ddfa33362140feea997351b77.js",
    "context": {
      "path": "js/165d7b0ddfa33362140feea997351b77.js"
    }
  },
  {
    "path": "js/16df9ef05001a1741857bf99f5a5738f.js",
    "context": {
      "path": "js/16df9ef05001a1741857bf99f5a5738f.js"
    }
  },
  {
    "path": "js/174ce8c99b1da026e642e20fdaf6b74c.js",
    "context": {
      "path": "js/174ce8c99b1da026e642e20fdaf6b74c.js"
    }
  },
  {
    "path": "js/1e73ecdfe65e5935eaa67f1defe75e0b.js",
    "context": {
      "path": "js/1e73ecdfe65e5935eaa67f1defe75e0b.js"
    }
  },
  {
    "path": "js/2a85c11e395a8380b5915443e926b569.js",
    "context": {
      "path": "js/2a85c11e395a8380b5915443e926b569.js"
    }
  },
  {
    "path": "js/34be5330971fdbd18985525bd994b0aa.js",
    "context": {
      "path": "js/34be5330971fdbd18985525bd994b0aa.js"
    }
  },
  {
    "path": "js/35c5f9e096d4da33d2a62031daf14248.js",
    "context": {
      "path": "js/35c5f9e096d4da33d2a62031daf14248.js"
    }
  },
  {
    "path": "js/3d70953a848219e749fedc2cdb906675.js",
    "context": {
      "path": "js/3d70953a848219e749fedc2cdb906675.js"
    }
  },
  {
    "path": "js/3e940a33e44b65c1c0af8bb80a893530.js",
    "context": {
      "path": "js/3e940a33e44b65c1c0af8bb80a893530.js"
    }
  },
  {
    "path": "js/544d012df7acf9c3f0920f67c9e322b9.js",
    "context": {
      "path": "js/544d012df7acf9c3f0920f67c9e322b9.js"
    }
  },
  {
    "path": "js/57d119d998d518b01f9d5ccb5e4d4c52.js",
    "context": {
      "path": "js/57d119d998d518b01f9d5ccb5e4d4c52.js"
    }
  },
  {
    "path": "js/67f6e2f99c3c3133e0dc669919fff5c5.js",
    "context": {
      "path": "js/67f6e2f99c3c3133e0dc669919fff5c5.js"
    }
  },
  {
    "path": "js/7045b35c5bd0e9c7cf59f1900eeeec41.js",
    "context": {
      "path": "js/7045b35c5bd0e9c7cf59f1900eeeec41.js"
    }
  },
  {
    "path": "js/7260bab328b0ad74815a5efb377bcc67.js",
    "context": {
      "path": "js/7260bab328b0ad74815a5efb377bcc67.js"
    }
  },
  {
    "path": "js/893de96f1b6da546bd7c814964723eca.js",
    "context": {
      "path": "js/893de96f1b6da546bd7c814964723eca.js"
    }
  },
  {
    "path": "js/93e29fe348ddc9b71aba9c842adc18b8.js",
    "context": {
      "path": "js/93e29fe348ddc9b71aba9c842adc18b8.js"
    }
  },
  {
    "path": "js/9455859483e31e4da0e28f10d0742c2a.js",
    "context": {
      "path": "js/9455859483e31e4da0e28f10d0742c2a.js"
    }
  },
  {
    "path": "js/9db10375d298678e53777a2347b87073.js",
    "context": {
      "path": "js/9db10375d298678e53777a2347b87073.js"
    }
  },
  {
    "path": "js/9f9b6e54f82a6bbc8bac9b89327024bc.js",
    "context": {
      "path": "js/9f9b6e54f82a6bbc8bac9b89327024bc.js"
    }
  },
  {
    "path": "js/a2261649751fa61b606222c9b2ea3b80.js",
    "context": {
      "path": "js/a2261649751fa61b606222c9b2ea3b80.js"
    }
  },
  {
    "path": "js/b0bade6d42c2702ca85774296cc507c4.js",
    "context": {
      "path": "js/b0bade6d42c2702ca85774296cc507c4.js"
    }
  },
  {
    "path": "js/cd1ed86c1e7f06d985fd71bc10bd4b04.js",
    "context": {
      "path": "js/cd1ed86c1e7f06d985fd71bc10bd4b04.js"
    }
  },
  {
    "path": "js/cecb447a04bbe3e8982190dd6e697120.js",
    "context": {
      "path": "js/cecb447a04bbe3e8982190dd6e697120.js"
    }
  },
  {
    "path": "js/d80b370d82680fc786dcc943a327b9f2.js",
    "context": {
      "path": "js/d80b370d82680fc786dcc943a327b9f2.js"
    }
  },
  {
    "path": "js/df80c5cbcb312a9c7c0b2ebb6ac5f592.js",
    "context": {
      "path": "js/df80c5cbcb312a9c7c0b2ebb6ac5f592.js"
    }
  },
  {
    "path": "js/f1e5dbc1ece900d164c2e9aa2d6a1386.js",
    "context": {
      "path": "js/f1e5dbc1ece900d164c2e9aa2d6a1386.js"
    }
  },
  {
    "path": "js/f3f02c438592c8e1bbe551f4dbbf4f5c.js",
    "context": {
      "path": "js/f3f02c438592c8e1bbe551f4dbbf4f5c.js"
    }
  },
  {
    "path": "js/faf9ce4e848522206b5c3043551fb2d7.js",
    "context": {
      "path": "js/faf9ce4e848522206b5c3043551fb2d7.js"
    }
  },
  {
    "path": "landing-page.html",
    "context": {
      "title": "Hotel Consultants in Delhi, Hospitality Management Company in India",
      "first_heading": "MAXIMIZE ROI OF YOUR HOTEL"
    }
  },
  {
    "path": "resort-management-company.html",
    "context": {
      "title": "Resort Management Company, Resort Management Consultants and Services",
      "first_heading": "RESORT MANAGEMENT COMPANY"
    }
  },
  {
    "path": "services.html",
    "context": {
      "title": "Hospitality Management Services, Hotel Management and Consulting",
      "first_heading": "HOTEL MANAGEMENT AND CONSULTING SERVICES"
    }
  },
  {
    "path": "thank-you.html",
    "context": {
      "title": "Hotel Consultants in Delhi, Hospitality Management Company in India",
      "first_heading": "THANK YOU"
    }
  }
]

Return only a JSON object mapping each path to its new basename (same extension). No other text.