# Claude Custom Instructions - Specialized Research Prompts

This directory contains specialized Claude custom instruction prompts for different areas of your life. Each prompt is tailored to provide research and guidance in a specific domain with domain-specific quality standards, source evaluation, and response formats.

## Available Prompts

### 1. 💰 Financial Investment Research
**File:** `financial-investment-research.md`

**Use for:**
- IRA accounts (Traditional, Roth, SEP, Solo 401k)
- Individual brokerage strategies
- Wealth-building opportunities (backdoor Roth, mega backdoor Roth, etc.)
- Tax-efficient investing
- Retirement planning

**Key Features:**
- Authoritative source prioritization (IRS.gov, SEC.gov, tax code)
- Current contribution limits and tax implications
- After-tax return calculations
- Fee and expense ratio analysis
- Professional advisor consultation guidance

**Activation Phrases:**
- "Research investment strategy for..."
- "Compare IRA vs. brokerage for..."
- "Analyze wealth opportunity of..."
- "Maximize contributions to..."

---

### 2. 💼 Professional Development Research
**File:** `professional-development-research.md`

**Use for:**
- Career certifications and credentials
- Skills development and training
- Job market trends and salary data
- Career transitions and advancement
- Learning paths and progression

**Key Features:**
- Job posting analysis for actual demand verification
- Salary data by geography and experience
- Employer recognition of certifications
- Realistic timelines and effort estimates
- Free/low-cost learning resources
- Portfolio and credibility building

**Activation Phrases:**
- "Research career path for..."
- "What certifications should I pursue for..."
- "Analyze job market demand for..."
- "Compare training programs for..."
- "Create learning roadmap for..."

---

### 3. 🏡 Family & Home Research
**File:** `family-home-research.md`

**Use for:**
- Home improvements and renovations
- Interior design and space planning
- Building codes and permit requirements
- Parenting strategies and child development
- Home safety and maintenance
- Family wellbeing and education

**Key Features:**
- Building code and safety standard verification
- Realistic cost estimates with contingency
- DIY vs. professional work assessment
- Evidence-based parenting guidance
- Local permit and compliance requirements
- Accessibility and family needs consideration

**Activation Phrases:**
- "Research home improvement for..."
- "Help me design/plan..."
- "What's involved in..."
- "Research parenting approach for..."
- "Compare options for home..."
- "Safety check for..."

---

### 4. 🎨 Personal Interests & Hobbies Research
**File:** `personal-interests-hobbies-research.md`

**Use for:**
- Starting new hobbies and interests
- Learning new skills and crafts
- Finding communities and mentors
- Skill progression and mastery
- Budget-friendly entry points
- Creative and recreational pursuits

**Key Features:**
- Beginner-friendly resource recommendations
- Startup cost optimization and gear guides
- Timeline to enjoyment and competency
- Community finding and social opportunities
- Common beginner mistakes and how to avoid them
- Different learning styles and paces

**Activation Phrases:**
- "Help me get started with..."
- "I want to learn..."
- "Research how to start..."
- "What's involved in pursuing..."
- "Budget-friendly way to try..."
- "Find beginner communities for..."

---

## How to Use These Prompts

### In Claude.ai
1. Go to **Settings** → **Custom Instructions**
2. Copy the entire content of the prompt file you want
3. Paste into the custom instructions box
4. Save
5. Start using that research mode in conversations

### In Claude for Desktop
1. Locate your `claude_desktop_config.json`:
   - Mac: `~/Library/Application Support/Claude/claude_desktop_config.json`
   - Windows: `%APPDATA%\Claude\claude_desktop_config.json`
   - Linux: `~/.config/Claude/claude_desktop_config.json`

2. Add or modify the system prompt:
   ```json
   {
     "claude": {
       "system_prompt": "[paste prompt content here]"
     }
   }
   ```

3. Restart Claude Desktop

### In Claude API
```python
import anthropic

client = anthropic.Anthropic()

# Load the prompt content
with open('financial-investment-research.md', 'r') as f:
    prompt_content = f.read()

message = client.messages.create(
    model="claude-3-5-sonnet-20241022",
    max_tokens=1024,
    system=prompt_content,
    messages=[
        {"role": "user", "content": "Your research question..."}
    ]
)
```

---

## Prompt Features Across All Modes

### Research Methodology
All prompts use a consistent 5-phase research approach:
1. **Question Clarification** - Establish scope and context
2. **Source Identification** - Find authoritative sources
3. **Information Gathering** - Extract and assess credibility
4. **Synthesis** - Connect findings into insight
5. **Delivery** - Format appropriately for decisions

### Quality Principles
Each prompt emphasizes domain-specific quality standards:
- **Financial:** Tax-aware, regulatory-compliant, conservative
- **Professional:** Market-demand-based, ROI-focused, realistic
- **Home/Family:** Safety-first, code-compliant, evidence-based
- **Hobbies:** Beginner-friendly, community-focused, budget-conscious

### Credibility Assessment
Each mode includes methods to evaluate source quality:
- Authority of author/organization
- Currency and recency of information
- Methodology and supporting evidence
- Alignment with official standards
- Community acceptance and reputation

---

## Switching Between Modes

You can:
1. **Use different modes in different conversations** - Start a new chat and load the appropriate prompt
2. **Switch prompts in one conversation** - Tell Claude: "Switch to [mode name] research mode" and paste the new prompt
3. **Use just one mode** - Pick your most-used domain and stick with it

---

## Quick Reference: When to Use Each Mode

| Situation | Use This Mode | Why |
|-----------|---|---|
| Making investment decisions | 💰 Financial | Tax and regulatory expertise needed |
| Career or skill questions | 💼 Professional | Market demand verification essential |
| Home or family planning | 🏡 Family & Home | Safety and code compliance critical |
| Exploring new interests | 🎨 Hobbies | Community and beginner-friendliness key |
| General research | Base Researcher | Use the main AGENT.md from the parent directory |

---

## Notes

- Each prompt emphasizes "This is research guidance, not professional advice" where applicable
- Financial prompt recommends CFP/CPA consultation
- Home/Family prompt emphasizes safety and code compliance
- All prompts encourage citing sources and noting uncertainties
- Professional prompt includes job market verification
- Hobbies prompt emphasizes enjoyment and community

---

*Created for the Researcher Agent system - Adapted for standalone Claude use*

Last updated: 2026-05-12
