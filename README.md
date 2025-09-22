# Stock Agent - AI-Powered Stock Analysis Tool

A comprehensive n8n workflow that provides intelligent stock analysis combining technical indicators, sentiment analysis, and multi-timeframe trading signals.

## Overview

Stock Agent is an automated trading analysis system built on n8n that delivers professional-grade stock analysis reports. The agent processes stock tickers through a structured 6-step framework, combining quantitative metrics, technical analysis across multiple timeframes, and real-time market sentiment to generate actionable trading insights.

## Features

### Multi-Timeframe Technical Analysis
- 1-minute chart analysis for scalping opportunities
- 5-minute charts for short-term entry/exit timing
- 15-minute analysis for swing trading setups
- Daily and weekly context for overall trend assessment

### Comprehensive Technical Indicators
- MACD signal line crosses and histogram divergence analysis
- RSI overbought/oversold levels with 30/70 thresholds
- Moving average alignment across 9, 21, 50, and 200 EMAs
- Volume confirmation and divergence detection
- Dynamic support and resistance level identification
- Trend line breakout and breakdown analysis

### Trading Signal Generation
- Clear BUY/SELL/HOLD recommendations with confidence levels
- Specific entry zones and stop-loss recommendations
- Multiple profit target levels with calculated risk/reward ratios
- Position sizing guidance based on volatility analysis
- Time horizon recommendations (scalp, day trade, swing)

### Real-Time Market Intelligence
- Advanced sentiment analysis using Tavily API
- 7-day lookback for comprehensive news coverage
- Analyst reports and price target aggregation
- Earnings announcements and competitive developments
- Market catalyst identification and risk assessment

## Architecture

### Core Components

**Chat Trigger Node**
- Webhook-based interface for user interactions
- Accepts stock ticker requests and follow-up queries

**AI Agent (LangChain)**
- Central orchestration engine using GPT-4o-mini
- Implements the 6-step analysis framework
- Synthesizes data from multiple sources into coherent reports

**OpenRouter Integration**
- Language model provider for intelligent analysis
- Handles complex reasoning and pattern recognition
- Generates human-readable trading recommendations

**Memory Buffer**
- Conversation context management
- Enables follow-up questions and analysis refinements
- Maintains session state for continuous interaction

**Stock Tool Workflow**
- Custom technical analysis engine
- Financial metrics extraction and processing
- Price chart generation and analysis

**Tavily Search Integration**
- Real-time news and sentiment gathering
- Advanced search with configurable depth
- Market development tracking and analysis

## Analysis Framework

### Step 1: Ticker Validation
- Identifies and confirms official stock ticker symbols
- Handles ambiguous requests with clarification prompts

### Step 2: Quantitative Analysis
- Extracts key financial metrics and ratios
- Generates fundamental analysis baseline
- Provides historical performance context

### Step 3: Technical Analysis
- Multi-timeframe chart analysis
- Technical indicator calculation and interpretation
- Support/resistance level identification

### Step 4: Signal Generation
- BUY/SELL signal analysis across timeframes
- Entry/exit level recommendations
- Risk management parameters

### Step 5: Sentiment Integration
- News flow analysis and market sentiment scoring
- Analyst coverage and recommendation aggregation
- Event impact assessment

### Step 6: Report Synthesis
- Comprehensive analysis compilation
- Cross-validation of signals and sentiment
- Final recommendations with risk disclaimers

## Output Format

Each analysis includes:

**Snapshot Section**
- 2-3 sentence overview with current market bias
- Quick assessment for immediate decision making

**Quantitative Metrics**
- Key financial ratios and performance indicators
- Fundamental analysis summary

**Multi-Timeframe Technicals**
- Detailed breakdown across 1m, 5m, 15m, and daily charts
- Technical indicator status and signal confirmation

**Trading Signals**
- Specific BUY/SELL recommendations with confidence levels
- Entry zones, stop losses, and profit targets
- Risk/reward ratio calculations

**Market Sentiment**
- Recent news highlights and market drivers
- Analyst sentiment and price target consensus

**Integrated Outlook**
- Forward-looking analysis incorporating all data sources
- Catalyst identification and risk assessment
- Trading strategy recommendations

**Risk Disclaimer**
- Educational purpose statement
- Risk management reminders

## Installation

### Prerequisites
- n8n instance with LangChain node support
- OpenRouter API access
- Tavily API subscription
- Custom stock data source (API or workflow)

### Setup Process

1. **Clone Repository**
   ```bash
   git clone https://github.com/yourusername/stock-agent.git
   cd stock-agent
   ```

2. **Import Workflow**
   - Import the JSON workflow file into your n8n instance
   - Configure node connections and settings

3. **Configure Credentials**
   - Set up OpenRouter API credentials
   - Configure Tavily API access
   - Update stock data source connections

4. **Update Placeholders**
   Replace the following placeholders in the workflow:
   - `YOUR_OPENROUTER_CREDENTIAL_ID`
   - `YOUR_TAVILY_API_KEY` 
   - `YOUR_WORKFLOW_ID`
   - `WEBHOOK_ID_PLACEHOLDER`
   - `UNIQUE_VERSION_ID`
   - `UNIQUE_INSTANCE_ID`

5. **Test Configuration**
   - Verify webhook endpoint accessibility
   - Test API connections and responses
   - Validate output format and accuracy

## Usage

### Basic Analysis Request
Send a stock ticker symbol to the chat interface:
```
Analyze AAPL
```

### Advanced Queries
Request specific analysis types:
```
Give me a swing trading setup for TSLA
What's the sentiment on NVDA this week?
Show me scalping signals for SPY
```

### Follow-up Questions
Continue conversations for deeper analysis:
```
What are the key resistance levels?
How does this compare to sector performance?
What's the risk/reward for this trade?
```

## API Integration

### Webhook Endpoint
```
POST /webhook/your-webhook-id
Content-Type: application/json

{
  "message": "Analyze AAPL",
  "user_id": "optional_user_identifier"
}
```

### Response Format
```json
{
  "analysis": {
    "ticker": "AAPL",
    "snapshot": "...",
    "signals": {...},
    "technicals": {...},
    "sentiment": {...}
  },
  "timestamp": "2025-01-XX",
  "confidence": "high"
}
```

## Configuration Options

### Analysis Parameters
- Timeframe selection (1m, 5m, 15m, 1h, 1d)
- Technical indicator sensitivity
- News lookback period (1-30 days)
- Confidence threshold settings

### Risk Management
- Default stop-loss percentages
- Position sizing algorithms
- Risk/reward ratio requirements
- Maximum position concentration

### Output Customization
- Report format preferences
- Chart inclusion options
- Disclaimer customization
- Language and tone settings

## Contributing

### Development Setup
1. Fork the repository
2. Create a feature branch
3. Make changes and test thoroughly
4. Submit a pull request with detailed description

### Code Standards
- Follow n8n workflow best practices
- Include comprehensive testing
- Document all configuration changes
- Maintain backward compatibility

## License

This project is licensed under the MIT License. See LICENSE file for details.

## Disclaimer

This tool is for educational and informational purposes only. It does not constitute financial advice or recommendations. Users should conduct their own research and consult with qualified financial advisors before making investment decisions. Past performance does not guarantee future results.

## Support

For issues, questions, or contributions:
- Create an issue on GitHub
- Check existing documentation
- Review n8n community resources
- Contact project maintainers

---

**Version**: 1.0.0  
**Last Updated**: January 2025  
**Compatibility**: n8n v1.0+, LangChain nodes v2.0+
