# 🚀 DEPLOYMENT GUIDE - AFFILIATE CONTENT FACTORY

## ⚡ QUICK START (5 Minutes)

### 1. Login to Your N8N Instance
- URL: Your n8n cloud instance or self-hosted URL
- Login: AlexHerchen@icloud.com / [your password]

### 2. Import Core Workflow
1. Go to **Workflows** → **Import from File**
2. Upload: `workflows/affiliate-core-workflow.json`
3. Click **Save** and **Activate**

### 3. Configure API Keys
1. Go to **Settings** → **Credentials**  
2. Add **OpenAI** credential:
   - Name: `openai-content-generator`
   - API Key: Your OpenAI key
3. (Optional) Add **Airtable** credential for tracking

### 4. Test with PokSignals
1. Copy webhook URL from the workflow
2. Open `interface/content-generator.html` in browser
3. Paste webhook URL and PokSignals affiliate link
4. Hit **Generate Content Arsenal**

### 5. Deploy Interface (Optional)
- Host `content-generator.html` anywhere (Netlify, GitHub Pages)
- Or use directly from local file

**🎯 YOU'RE LIVE - Start generating content at scale!**

---

## 🔧 DETAILED SETUP

### N8N Workflow Configuration

#### Core Workflow Nodes:
1. **Webhook Input** - Receives affiliate URL + parameters
2. **Product Scraper** - Extracts product details
3. **AI Content Generator** - Creates platform-specific content  
4. **Content Structurer** - Formats output by platform
5. **Success/Error Handlers** - Manages responses

#### Environment Variables:
Add these in n8n Settings → Environment:
```bash
OPENAI_API_KEY=your_openai_key
AIRTABLE_BASE_ID=your_airtable_base (optional)
AIRTABLE_TABLE_ID=your_table_id (optional)
```

### Content Output Structure:
```json
{
  "affiliate_url": "https://whop.com/product?a=link",
  "total_pieces": 25,
  "generated_at": "2026-02-01T00:40:00Z",
  "content_by_platform": {
    "tiktok": [
      {
        "type": "video_script",
        "title": "Hook Title",
        "content": "Full script...",
        "hooks": ["Opening hook", "CTA"],
        "ready_to_post": true
      }
    ],
    "twitter": [...],
    "instagram": [...],
    "youtube": [...],
    "linkedin": [...]
  }
}
```

---

## 🎛️ USAGE PATTERNS

### 1. Quick Single Product
**Input:**
```json
{
  "affiliate_url": "https://whop.com/product?a=yourlink"
}
```

### 2. Targeted Campaign  
**Input:**
```json
{
  "affiliate_url": "https://whop.com/product?a=yourlink",
  "target_audience": "Pokemon card collectors",
  "content_quantity": 7,
  "international_markets": ["US", "UK", "AU"]
}
```

### 3. Multi-Product Batch
Set up multiple webhook calls or create a batch processor workflow.

---

## 📊 MONITORING & OPTIMIZATION

### Performance Tracking
- **Content Database:** Track generated campaigns in Airtable
- **Webhook Logs:** Monitor generation success/failure rates
- **Output Quality:** Review and iterate on prompt engineering

### A/B Testing Framework
1. Generate multiple content variants
2. Track platform-specific performance
3. Optimize high-performing angles
4. Scale winning content patterns

### Cost Management
- **OpenAI Usage:** ~$0.50-1.00 per campaign (25 pieces)
- **N8N Cloud:** Standard execution limits
- **Optimization:** Cache product data, reuse successful templates

---

## 🔄 SCALING OPERATIONS

### Phase 1: Manual Testing (Week 1)
- Test 5-10 products
- Validate output quality
- Optimize content templates

### Phase 2: Process Automation (Week 2-3)
- Batch processing workflows
- Scheduled content generation
- Performance analytics integration

### Phase 3: Product Launch (Week 4+)
- Sell the system as SaaS
- White-label for agencies
- Scale to 100+ products/day

---

## 🛠️ TROUBLESHOOTING

### Common Issues:
1. **Webhook timeout** → Increase n8n execution timeout
2. **Content quality low** → Refine OpenAI prompts
3. **Platform formatting** → Check output structure logic
4. **Rate limits** → Add delay nodes between API calls

### Optimization Tips:
- **Cache product data** for repeat campaigns
- **Template successful angles** for reuse
- **A/B test hook variations** systematically
- **Monitor token usage** vs. content quality

---

## 🚀 NEXT LEVEL FEATURES

### Advanced Workflows:
1. **Competitor Analysis Pipeline** - Auto-research competing products
2. **Performance Feedback Loop** - Analytics → content optimization
3. **Multi-Language Generation** - International market variants
4. **Visual Content Creator** - Auto-generate images/carousels
5. **Posting Automation** - Direct social media scheduling

### Integration Options:
- **Social Media APIs** - Direct posting to platforms
- **Analytics Tools** - Performance tracking integration
- **CRM Systems** - Lead capture and management
- **Payment Processing** - Monetize the pipeline itself

---

**🪖 DEPLOYMENT STATUS: READY FOR BATTLE**

Your affiliate content factory is locked and loaded. Time to scale.

**Next Mission:** Import the workflow and test with PokSignals. Report back with results, Soldier.