# The Org - Multi-Agent System User Manual

## Table of Contents
1. [Overview](#overview)
2. [Quick Start Guide](#quick-start-guide)
3. [System Requirements](#system-requirements)
4. [Installation & Setup](#installation--setup)
5. [Configuration](#configuration)
6. [Agent Descriptions](#agent-descriptions)
7. [Usage Examples](#usage-examples)
8. [Advanced Features](#advanced-features)
9. [Troubleshooting](#troubleshooting)
10. [Best Practices](#best-practices)
11. [Support & Community](#support--community)

---

## Overview

The Org is a sophisticated multi-agent system built on the ElizaOS framework, designed to handle various organizational functions through specialized AI agents. Each agent has unique capabilities and can work independently or collaboratively to manage different aspects of your organization.

### Key Features
- **5 Specialized Agents** for different organizational roles
- **Multi-Platform Integration** (Discord, Telegram, Twitter)
- **Persistent Memory & State Management**
- **Advanced LLM Integration** (OpenAI, Anthropic, Local AI)
- **Comprehensive Load Testing Suite**
- **Dynamic Onboarding & Configuration**

---

## Quick Start Guide

### 1. Install Dependencies
```bash
npm install
```

### 2. Configure Environment
Create a `.env` file in the root directory:
```env
# Basic Configuration
POSTGRES_URL=postgresql://user:password@host:port/database
OPENAI_API_KEY=your_openai_api_key
ANTHROPIC_API_KEY=your_anthropic_api_key
```

### 3. Start All Agents
```bash
npm start
```

### 4. Start Specific Agents
```bash
npm start -- --devRel --projectManager
```

---

## System Requirements

### Minimum Requirements
- **Node.js**: Latest LTS version
- **Bun**: v1.0 or higher
- **Memory**: 4GB RAM
- **Storage**: 2GB free space

### Recommended Requirements
- **Node.js**: Latest stable version
- **Bun**: Latest version
- **Memory**: 8GB RAM
- **Storage**: 5GB free space
- **Database**: PostgreSQL instance

### Platform Access Requirements
- Discord: Application ID and Bot Token
- Telegram: Bot Token
- Twitter: Username, Email, Password (optional: 2FA Secret)

---

## Installation & Setup

### 1. Clone and Install
```bash
git clone <repository-url>
cd the-org
npm install
```

### 2. Database Setup
The system uses PostgreSQL for persistent storage. You can either:

**Option A: Use Existing PostgreSQL**
```env
POSTGRES_URL=postgresql://username:password@localhost:5432/database_name
```

**Option B: Use SQLite (Local Development)**
```env
# Leave POSTGRES_URL empty for SQLite fallback
```

### 3. Environment Configuration
Copy the example configuration and customize:

```bash
cp .env.example .env
# Edit .env with your actual credentials
```

---

## Configuration

### Environment Variables Reference

#### General Configuration
```env
# Database
POSTGRES_URL=postgresql://user:password@host:port/database

# AI Providers
OPENAI_API_KEY=your_openai_api_key
ANTHROPIC_API_KEY=your_anthropic_api_key
```

#### Agent-Specific Configuration

##### Community Manager (Eli5)
```env
COMMUNITY_MANAGER_DISCORD_APPLICATION_ID=your_discord_app_id
COMMUNITY_MANAGER_DISCORD_API_TOKEN=your_discord_bot_token
```

##### Developer Relations (Eddy)
```env
DEV_REL_DISCORD_APPLICATION_ID=your_discord_app_id
DEV_REL_DISCORD_API_TOKEN=your_discord_bot_token
DEVREL_IMPORT_KNOWLEDGE=true
```

##### Community Liaison (Ruby)
```env
LIAISON_DISCORD_APPLICATION_ID=your_discord_app_id
LIAISON_DISCORD_API_TOKEN=your_discord_bot_token
```

##### Project Manager (Jimmy)
```env
PROJECT_MANAGER_DISCORD_APPLICATION_ID=your_discord_app_id
PROJECT_MANAGER_DISCORD_API_TOKEN=your_discord_bot_token
PROJECT_MANAGER_TELEGRAM_BOT_TOKEN=your_telegram_bot_token
```

##### Social Media Manager (Laura)
```env
SOCIAL_MEDIA_MANAGER_DISCORD_APPLICATION_ID=your_discord_app_id
SOCIAL_MEDIA_MANAGER_DISCORD_API_TOKEN=your_discord_bot_token
TWITTER_USERNAME=your_twitter_username
TWITTER_EMAIL=your_twitter_email
TWITTER_PASSWORD=your_twitter_password
TWITTER_2FA_SECRET=your_twitter_2fa_secret
```

---

## Agent Descriptions

### 🛡️ Eli5 - Community Manager
**Role**: Community health and user engagement
**Platforms**: Discord, Twitter
**Key Capabilities**:
- Welcome new users automatically
- Moderate discussions and handle conflicts
- Timeout users who violate guidelines
- Maintain positive community atmosphere

**Setup Commands**:
- Set greeting preferences: "Should I greet new users?"
- Configure greeting channel: "Use #general for greetings"
- Customize greeting message: "Welcome message: Hello and welcome!"

### 👨‍💻 Eddy - Developer Relations
**Role**: Technical support and documentation assistance
**Platforms**: Discord
**Key Capabilities**:
- Answer technical questions using documentation
- Provide code examples and explanations
- Help with ElizaOS implementation
- Maintain knowledge base of common issues

**Usage Examples**:
- "How do I implement custom actions in ElizaOS?"
- "Can you help me with plugin integration?"
- "Where can I find the AgentRuntime documentation?"

### 🔗 Ruby - Community Liaison
**Role**: Cross-platform coordination and information sharing
**Platforms**: Discord, Telegram, Slack
**Key Capabilities**:
- Monitor discussions across platforms
- Provide platform-specific information
- Recommend appropriate channels for questions
- Coordinate cross-platform events

**Usage Examples**:
- "What's being discussed in the Telegram group?"
- "Where should I ask about deployment?"
- "Can you coordinate a cross-platform hackathon?"

### 📊 Jimmy - Project Manager
**Role**: Project coordination and team management
**Platforms**: Discord, Telegram
**Key Capabilities**:
- Track team member updates and progress
- Schedule and manage check-ins
- Generate progress reports
- Coordinate team activities

**Setup Process**:
1. "Set up daily check-ins for the team"
2. Configure team members and their update formats
3. Set check-in schedules and frequencies
4. Review generated reports

### 📱 Laura - Social Media Manager
**Role**: Content creation and social media management
**Platforms**: Discord, Twitter
**Key Capabilities**:
- Draft and approve social media posts
- Cross-platform content distribution
- Maintain brand voice and messaging
- Handle Twitter posting with approval workflow

**Usage Examples**:
- "Create a tweet about our new feature"
- "Post this announcement to all platforms"
- "Draft content for our product launch"

---

## Usage Examples

### Setting Up Community Management

1. **Configure Greeting System**:
```
User: "Should I greet new users?"
Eli5: "Yes, I'll help you set up greetings. Which channel should I use?"
User: "Use #welcome channel"
Eli5: "Got it! What message should I use?"
User: "Welcome to our community! Feel free to introduce yourself."
```

2. **Moderation Actions**:
```
User: "This user is being disruptive"
Eli5: "I'll handle it. Let me talk to them first."
```

### Project Management Workflow

1. **Set Up Team Check-ins**:
```
User: "Set up daily check-ins for the development team"
Jimmy: "I'll help you configure check-ins. What type would you like?"
User: "Daily standup at 9 AM UTC for the #dev-team channel"
```

2. **Add Team Members**:
```
User: "Add team members:
Section: Frontend
Telegram: @alice_dev
Update Fields: What did you complete? What's next? Any blockers?"
Jimmy: "Team members added successfully!"
```

3. **Generate Reports**:
```
User: "Generate a daily standup report"
Jimmy: "Here's the team progress report with productivity analysis..."
```

### Social Media Management

1. **Create Twitter Posts**:
```
User: "Tweet about our new AI feature launch"
Laura: "I'll tweet this: 'Introducing our new AI-powered automation feature...'
Waiting for approval from an admin"
Admin: "post"
Laura: "https://twitter.com/yourhandle/status/123456789"
```

### Developer Support

1. **Technical Questions**:
```
Developer: "How do I create custom actions in ElizaOS?"
Eddy: "Here's how to implement custom actions:

```typescript
export const myCustomAction: Action = {
  name: 'MY_CUSTOM_ACTION',
  // ... implementation
}
```

Refer to the documentation for more details."
```

---

## Advanced Features

### Load Testing

Run comprehensive scalability tests:
```bash
npm run test:scale
```

The system includes a sophisticated load testing suite that:
- Tests agent performance at different scales (2-2000 agents)
- Identifies breaking points and optimal configurations
- Generates detailed performance reports
- Provides scalability recommendations

### Custom Plugins

The system supports custom plugins for extending functionality:

1. Create plugin in `src/[agent]/plugins/`
2. Implement required interfaces
3. Register plugin with agent
4. Test functionality

### Multi-Platform Coordination

Agents can coordinate across platforms:
- Discord ↔ Telegram message bridging
- Cross-platform user tracking
- Unified reporting across platforms
- Synchronized configuration management

---

## Troubleshooting

### Common Issues

#### 1. "No agents available" Error
**Solution**: Check environment variables and platform configurations
```bash
# Verify Discord bot tokens
# Ensure at least one platform is configured per agent
```

#### 2. Database Connection Issues
**Solution**: Verify PostgreSQL connection or use SQLite fallback
```env
# For local development, remove POSTGRES_URL to use SQLite
# POSTGRES_URL=
```

#### 3. Agent Not Responding
**Checks**:
- Bot has proper permissions in Discord server
- Bot is online and connected
- Environment variables are correctly set
- Database is accessible

#### 4. Twitter Integration Issues
**Solution**: Verify Twitter credentials and 2FA setup
```env
TWITTER_USERNAME=your_username
TWITTER_EMAIL=your_email
TWITTER_PASSWORD=your_password
TWITTER_2FA_SECRET=your_2fa_secret  # If 2FA enabled
```

### Debug Mode

Enable detailed logging:
```bash
DEBUG=true npm start
```

### Health Checks

Monitor agent status:
```bash
# Check running processes
npm run health-check

# View agent logs
npm run logs
```

---

## Best Practices

### Security
- Store sensitive credentials in `.env` file
- Never commit API keys to version control
- Use environment-specific configurations
- Regularly rotate API keys and tokens

### Performance
- Monitor memory usage during high load
- Use PostgreSQL for production deployments
- Configure appropriate check-in frequencies
- Regularly clean up old data

### Organization
- Assign specific roles to different agents
- Configure clear boundaries between agent responsibilities
- Use consistent naming conventions
- Document custom configurations

### Maintenance
- Keep dependencies updated
- Monitor agent performance metrics
- Regular database maintenance
- Backup configuration settings

---

## Support & Community

### Getting Help
- **Documentation**: Full technical specs in `/src/[agent]/spec.md`
- **Issues**: Report bugs via GitHub issues
- **Examples**: Check `/tests/` for usage examples

### Contributing
- Follow the existing code structure
- Add tests for new features
- Update documentation
- Submit pull requests for review

### Community Resources
- Discord server for real-time support
- GitHub discussions for feature requests
- Wiki for community-contributed guides

---

## Appendix

### Agent Command Reference

#### Community Manager (Eli5)
- `greet new users` - Enable/disable user greeting
- `timeout @user` - Moderate disruptive users
- `set greeting message` - Customize welcome text

#### Developer Relations (Eddy)
- `how do I...` - Ask technical questions
- `show documentation for...` - Get specific docs
- `example of...` - Request code examples

#### Community Liaison (Ruby)
- `what's happening in [platform]` - Get platform updates
- `where should I ask about...` - Get channel recommendations
- `coordinate [event]` - Plan cross-platform events

#### Project Manager (Jimmy)
- `set up check-ins` - Configure team check-ins
- `add team member` - Register new team members
- `generate report` - Create progress reports
- `list team members` - View current team
- `my updates format` - Get personal update template

#### Social Media Manager (Laura)
- `tweet about...` - Create Twitter posts
- `post to all platforms` - Cross-platform posting
- `draft content for...` - Create content drafts

### Configuration Templates

See the individual agent specifications in `/src/[agent]/spec.md` for detailed configuration options and advanced setup instructions.

---

*This manual is regularly updated. For the latest version and additional resources, check the project repository.*