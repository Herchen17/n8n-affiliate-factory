# N8N CREDENTIALS SETUP

## 🔑 REQUIRED API KEYS

### 1. OpenAI API Key
- **Purpose:** Content generation engine
- **Setup:** n8n Settings → Credentials → Add New → OpenAI
- **Name:** `openai-content-generator`
- **Key:** Your OpenAI API key

### 2. Airtable (Optional - for content tracking)
- **Purpose:** Content database and performance tracking  
- **Setup:** n8n Settings → Credentials → Add New → Airtable
- **Name:** `airtable-content-db`
- **Token:** Your Airtable personal access token

### 3. Environment Variables
Add these to your n8n instance:

```bash
# Core Settings
AIRTABLE_BASE_ID=your_airtable_base_id
AIRTABLE_TABLE_ID=your_content_table_id

# Optional: Enhanced scraping
FIRECRAWL_API_KEY=your_firecrawl_key
```

## 🚀 QUICK SETUP CHECKLIST

1. ✅ Import `affiliate-core-workflow.json` 
2. ✅ Add OpenAI credentials
3. ✅ Set environment variables
4. ✅ Test webhook endpoint
5. ✅ Validate output format

## 📋 AIRTABLE TABLE STRUCTURE

Create table: **Affiliate Content Campaigns**

Columns:
- `affiliate_url` (URL)
- `generated_at` (Date)  
- `total_pieces` (Number)
- `content_data` (Long text)
- `status` (Single select: Generated, Posted, Optimized)
- `performance_notes` (Long text)

## 🔗 WEBHOOK USAGE

**Endpoint:** `https://your-n8n-instance.com/webhook/affiliate-generator`

**POST Request:**
```json
{
  "affiliate_url": "https://whop.com/product?a=yourlink",
  "target_audience": "Pokemon card collectors",
  "content_quantity": 5,
  "international_markets": ["US", "UK", "AU", "CA"]
}
```

**Response:**
```json
{
  "affiliate_url": "...",
  "total_pieces": 25,
  "content_by_platform": {
    "tiktok": [...],
    "twitter": [...], 
    "instagram": [...],
    "youtube": [...],
    "linkedin": [...]
  }
}
```

Next: Building platform-specific optimization modules...