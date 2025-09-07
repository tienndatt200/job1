<html>
<html lang="en"><head>
	<meta charset="UTF-8">
	<meta name="awa-expId" content="vscw_aaflight1016_treatment:103440;">
	<meta name="awa-env" content="prod">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta name="google-site-verification" content="hNs7DXrTySP_X-0P_AC0WulAXvUwgSXEmgfcO2r79dw">

	<!-- Twitter and Facebook OpenGraph Metadata-->
	<meta name="twitter:card" content="summary_large_image">
	<meta name="twitter:site" content="@code">

	<meta name="description" content="Find out how to set-up and get the most from Visual Studio Code.  Optimized for building and debugging modern web and cloud applications.  Visual Studio Code is free and available on your favorite platform - Linux, macOS, and Windows.">

<!-- Twitter and Facebook OpenGraph Metadata-->
<meta property="og:title" content="Documentation for Visual Studio Code">
<meta property="og:description" content="Find out how to set-up and get the most from Visual Studio Code.  Optimized for building and debugging modern web and cloud applications.  Visual Studio Code is free and available on your favorite platform - Linux, macOS, and Windows.">
<meta property="og:image" content="https://code.visualstudio.com/opengraphimg/opengraph-gettingstarted.png">
<meta property="og:url" content="https://code.visualstudio.com/docs">
<link href="https://code.visualstudio.com/docs" rel="canonical">


	<link rel="shortcut icon" href="/assets/favicon.ico" sizes="128x128">
	<link rel="apple-touch-icon" href="/assets/apple-touch-icon.png">

	<title>Documentation for Visual Studio Code</title>

	<link rel="stylesheet" href="/vendor/bootstrap/css/bootstrap.min.css">
	<link rel="stylesheet" href="/dist/v2/style.css">

	<script src="https://consentdeliveryfd.azurefd.net/mscc/lib/v2/wcp-consent.js"></script>
	<script type="text/javascript" src="https://js.monitor.azure.com/scripts/c/ms.analytics-web-4.min.js"></script>
	
	<script type="text/javascript">
	// Leave as var; siteConsent is initialized and referenced elsewhere.
	var siteConsent = null;
	
	const GPC_DataSharingOptIn = false;
	WcpConsent.onInitCallback(function () {
		window.appInsights = new oneDS.ApplicationInsights();
		window.appInsights.initialize({
			instrumentationKey: "1a3eb3104447440391ad5f2a6ee06a0a-62879566-bc58-4741-9650-302bf2af703f-7103",
			propertyConfiguration: {
				userConsented: false,
				gpcDataSharingOptIn: false,
				callback: {
					userConsentDetails: siteConsent ? siteConsent.getConsent : undefined
				},
			},
			cookieCfg: {
				ignoreCookies: ["MSCC"]
			},
			webAnalyticsConfiguration:{ // Web Analytics Plugin configuration
				urlCollectQuery: true,
				urlCollectHash: true,
				autoCapture: {
					scroll: true,
					pageView: true,
					onLoad: true,
					onUnload: true,
					click: true,
					resize: true,
					jsError: true
				}
			}
		}, []);
	
		window.appInsights.getPropertyManager().getPropertiesContext().web.gpcDataSharingOptIn = GPC_DataSharingOptIn;
	});
	</script>
	<link rel="alternate" type="application/atom+xml" title="RSS Feed for code.visualstudio.com" href="/feed.xml">
</head>

<body class="win">
	<!-- Setting theme here to avoid FOUC -->
	<script>
		function setTheme(themeName) {
			if (themeName === 'dark') {
				document.documentElement.removeAttribute('data-theme'); // dark is default, so no data-theme attribute needed
			}

			if (themeName === 'light') {
				document.documentElement.setAttribute('data-theme', themeName);
			}
			return;
		}

		// Determine initial theme: user preference or system preference
		let theme = localStorage.getItem('theme') || (window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light');
		setTheme(theme); // Apply the initial theme

		// Listen for changes in the system theme preference
		window.matchMedia('(prefers-color-scheme: dark)').addListener(e => {
			if (!localStorage.getItem('theme')) { // Only if no user preference is saved
				setTheme(e.matches ? 'dark' : 'light');
			}
		});
	</script>

	<div id="main">
		<div class="navbar-fixed-container">
			<div class="navbar navbar-inverse navbar-fixed-top affix-top" data-spy="affix" data-offset-top="1">
				<div id="cookie-banner"></div>		<nav role="navigation" aria-label="Top Level">
					<div class="container">
						<div class="nav navbar-header">
							<a class="navbar-brand" href="/"><span>Visual Studio Code</span></a>
							<div class="tabloopElement" tabindex="0" style="display: none;"></div><button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".navbar-collapse" aria-label="Expand and Collapse Menu">
								<span class="icon-bar"></span>
								<span class="icon-bar"></span>
								<span class="icon-bar"></span>
							</button>
						</div>
						<div class="navbar-collapse collapse" style="max-height: min(60vh, 450px);">
							<ul class="nav navbar-nav navbar-left">
								<li class="active"><a id="nav-docs" href="/docs">Docs</a></li>
								<li><a id="nav-updates" href="/updates">Updates</a></li>
								<li><a id="nav-blogs" href="/blogs">Blog</a></li>
								<li><a id="nav-extend" href="/api">API</a></li>
								<li><a href="https://marketplace.visualstudio.com/VSCode" target="_blank" rel="noopener" id="nav-extensions">Extensions</a></li>
								<li><a id="nav-mcp" href="/mcp">MCP</a></li>
								<li><a id="nav-faqs" href="/docs/supporting/faq">FAQ</a></li>
								<li class="search visible-xs visible-sm"><a href="/Search">Search</a></li>
								<li><a id="nav-events" href="/dev-days">Dev Days</a></li>
							</ul>
		
							<ul class="nav navbar-nav navbar-right" role="presentation">
								<li>
									<button type="button" class="theme-switch" id="theme-toggle">
										<img class="theme-icon-light" src="/assets/icons/theme-light.svg" alt="Switch to the dark theme">
										<img class="theme-icon-dark" src="/assets/icons/theme-dark.svg" alt="Switch to the light theme">
									</button>
								</li>
								<li>
									<a href="/Search" title="Search" class="btn search-btn" id="nav-search">
										<img class="search-icon-light" src="/assets/icons/search.svg" width="16px" height="16px" alt="Search">
										<img class="search-icon-dark" src="/assets/icons/search-dark.svg" width="16px" height="16px" alt="Search">
									</a>
								</li>
								<li class="search" role="presentation">
									<form class="nav-search search-form" role="search" aria-label="Search">
										<div class="input-group" role="presentation">
											<input type="text" name="q" class="search-box form-control" placeholder="Search Docs" aria-label="Search text">
											<span class="input-group-btn">
												<button tabindex="0" class="btn" type="submit" aria-label="Search">
													<img class="search-icon-dark" src="/assets/icons/search-dark.svg" alt="Search">
													<img class="search-icon-light" src="/assets/icons/search.svg" alt="Search">
												</button>
											</span>
										<span class="search-shortcut-overlay">Ctrl+Shift+P</span></div>
									</form>						</li>
								<!-- this was hiden in the home and download page, keeping it for now -->
								<li><a class="link-button" href="/Download" id="nav-download">
										<span>Download</span></a><div class="tabloopElement" tabindex="0" style="display: none;"></div></li>
							</ul>
						</div>
					</div>
				</nav>
			</div>
		</div>		<div data-announcement-version="2025-08-25-dev-days" class="updates-banner">
			<div class="container">
				<p class="message">Join a <a href="/dev-days" id="banner-link-dev-days">VS Code Dev Days event</a> near you to learn about AI-assisted development in VS Code.</p>
			</div>
			<div tabindex="0" role="button" title="Dismiss this update" class="dismiss-btn" id="banner-dismiss-btn"><span class="sr-only">Dismiss this update</span><span aria-hidden="true" class="glyph-icon"></span></div>
		</div>		<!-- This div wraps around the entire site -->
		<!-- The body itself should already have a main tag -->
		<div id="main-content">
			<div class="container body-content docs landing-page">
	<div class="row">
		<div class="col-xs-12 col-md-2 docs-navbar-container"> <nav id="docs-navbar" aria-label="Topics" class="docs-nav visible-md visible-lg">
  <ul class="nav" id="main-nav">
  <li>
    <a class="docs-home" href="/docs">Overview</a>
  </li>
  
<li class="panel ">
  <a class="area" role="button" href="#setup-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Setup</a>
  <ul id="setup-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/setup/setup-overview">Overview</a>
        </li>
          
        <li>
          <a href="/docs/setup/linux">Linux</a>
        </li>
          
        <li>
          <a href="/docs/setup/mac">macOS</a>
        </li>
          
        <li>
          <a href="/docs/setup/windows">Windows</a>
        </li>
          
        <li>
          <a href="/docs/setup/vscode-web">VS Code for the Web</a>
        </li>
          
        <li>
          <a href="/docs/setup/raspberry-pi">Raspberry Pi</a>
        </li>
          
        <li>
          <a href="/docs/setup/network">Network</a>
        </li>
          
        <li>
          <a href="/docs/setup/additional-components">Additional Components</a>
        </li>
          
        <li>
          <a href="/docs/setup/enterprise">Enterprise</a>
        </li>
          
        <li>
          <a href="/docs/setup/uninstall">Uninstall</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#getstarted-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Get Started</a>
  <ul id="getstarted-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/getstarted/getting-started">VS Code Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/getstarted/copilot-quickstart">Copilot Quickstart</a>
        </li>
          
        <li>
          <a href="/docs/getstarted/userinterface">User Interface</a>
        </li>
          
        <li>
          <a href="/docs/getstarted/personalize-vscode">Personalize VS Code</a>
        </li>
          
        <li>
          <a href="/docs/getstarted/extensions">Install Extensions</a>
        </li>
          
        <li>
          <a href="/docs/getstarted/tips-and-tricks">Tips and Tricks</a>
        </li>
          
        <li>
          <a href="/docs/getstarted/introvideos">Intro Videos</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#configure-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Configure</a>
  <ul id="configure-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/configure/locales">Display Language</a>
        </li>
          
        <li>
          <a href="/docs/configure/custom-layout">Layout</a>
        </li>
          
        <li>
          <a href="/docs/configure/keybindings">Keyboard Shortcuts</a>
        </li>
          
        <li>
          <a href="/docs/configure/settings">Settings</a>
        </li>
          
        <li>
          <a href="/docs/configure/settings-sync">Settings Sync</a>
        </li>
          
<li class="panel">
  <a class="area disabled" tabindex="-1" aria-disabled="true">Extensions</a>
  <ul id="configure-extensions-articles" class="collapse in" aria-expanded="true">

        <li>
          <a href="/docs/configure/extensions/extension-marketplace">Extension Marketplace</a>
        </li>
          
        <li>
          <a href="/docs/configure/extensions/extension-runtime-security">Extension Runtime Security</a>
        </li>
          
  </ul>
</li>
        
        <li>
          <a href="/docs/configure/themes">Themes</a>
        </li>
          
        <li>
          <a href="/docs/configure/profiles">Profiles</a>
        </li>
          
<li class="panel collapsed">
  <a class="area" role="button" href="#configure-accessibility-articles" data-toggle="collapse" aria-expanded="false">Accessibility</a>
  <ul id="configure-accessibility-articles" class="collapse " aria-expanded="false">

        <li>
          <a href="/docs/configure/accessibility/accessibility">Overview</a>
        </li>
          
        <li>
          <a href="/docs/configure/accessibility/voice">Voice Interactions</a>
        </li>
          
  </ul>
</li>
        
        <li>
          <a href="/docs/configure/command-line">Command Line Interface</a>
        </li>
          
        <li>
          <a href="/docs/configure/telemetry">Telemetry</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#editing-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Edit code</a>
  <ul id="editing-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/editing/codebasics">Basic Editing</a>
        </li>
          
        <li>
          <a href="/docs/editing/intellisense">IntelliSense</a>
        </li>
          
        <li>
          <a href="/docs/editing/editingevolved">Code Navigation</a>
        </li>
          
        <li>
          <a href="/docs/editing/refactoring">Refactoring</a>
        </li>
          
        <li>
          <a href="/docs/editing/userdefinedsnippets">Snippets</a>
        </li>
          
<li class="panel collapsed">
  <a class="area" role="button" href="#editing-workspaces-articles" data-toggle="collapse" aria-expanded="false">Workspaces</a>
  <ul id="editing-workspaces-articles" class="collapse " aria-expanded="false">

        <li>
          <a href="/docs/editing/workspaces/workspaces">Overview</a>
        </li>
          
        <li>
          <a href="/docs/editing/workspaces/multi-root-workspaces">Multi-root Workspaces</a>
        </li>
          
        <li>
          <a href="/docs/editing/workspaces/workspace-trust">Workspace Trust</a>
        </li>
          
  </ul>
</li>
        
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#debugtest-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Build, Debug, Test</a>
  <ul id="debugtest-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/debugtest/tasks">Tasks</a>
        </li>
          
        <li>
          <a href="/docs/debugtest/debugging">Debugging</a>
        </li>
          
        <li>
          <a href="/docs/debugtest/debugging-configuration">Debug Configuration</a>
        </li>
          
        <li>
          <a href="/docs/debugtest/testing">Testing</a>
        </li>
          
        <li>
          <a href="/docs/debugtest/port-forwarding">Port Forwarding</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#copilot-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">GitHub Copilot</a>
  <ul id="copilot-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/copilot/overview">Overview</a>
        </li>
          
        <li>
          <a href="/docs/copilot/setup">Setup</a>
        </li>
          
        <li>
          <a href="/docs/copilot/getting-started">Quickstart</a>
        </li>
          
<li class="panel">
  <a class="area disabled" tabindex="-1" aria-disabled="true">Chat</a>
  <ul id="copilot-chat-articles" class="collapse in" aria-expanded="true">

        <li>
          <a href="/docs/copilot/chat/copilot-chat">Chat Overview</a>
        </li>
          
        <li>
          <a href="/docs/copilot/chat/copilot-chat-context">Manage Context</a>
        </li>
          
        <li>
          <a href="/docs/copilot/chat/chat-ask-mode">Ask Mode</a>
        </li>
          
        <li>
          <a href="/docs/copilot/chat/copilot-edits">Edit Mode</a>
        </li>
          
        <li>
          <a href="/docs/copilot/chat/chat-agent-mode">Agent Mode</a>
        </li>
          
        <li>
          <a href="/docs/copilot/chat/inline-chat">Inline Chat</a>
        </li>
          
        <li>
          <a href="/docs/copilot/chat/prompt-crafting">Prompt Engineering</a>
        </li>
          
  </ul>
</li>
        
        <li>
          <a href="/docs/copilot/ai-powered-suggestions">Code Completions</a>
        </li>
          
        <li>
          <a href="/docs/copilot/copilot-coding-agent">Copilot Coding Agent</a>
        </li>
          
<li class="panel">
  <a class="area disabled" tabindex="-1" aria-disabled="true">Customize Copilot</a>
  <ul id="copilot-customization-articles" class="collapse in" aria-expanded="true">

        <li>
          <a href="/docs/copilot/customization/overview">Overview</a>
        </li>
          
        <li>
          <a href="/docs/copilot/customization/custom-instructions">Custom Instructions</a>
        </li>
          
        <li>
          <a href="/docs/copilot/customization/prompt-files">Prompt Files</a>
        </li>
          
        <li>
          <a href="/docs/copilot/customization/custom-chat-modes">Chat Modes</a>
        </li>
          
        <li>
          <a href="/docs/copilot/customization/language-models">Language Models</a>
        </li>
          
        <li>
          <a href="/docs/copilot/customization/mcp-servers">MCP</a>
        </li>
          
  </ul>
</li>
        
<li class="panel">
  <a class="area disabled" tabindex="-1" aria-disabled="true">Guides</a>
  <ul id="copilot-guides-articles" class="collapse in" aria-expanded="true">

        <li>
          <a href="/docs/copilot/guides/notebooks-with-ai">Edit Notebooks with AI</a>
        </li>
          
        <li>
          <a href="/docs/copilot/guides/test-with-copilot">Test with AI</a>
        </li>
          
        <li>
          <a href="/docs/copilot/guides/debug-with-copilot">Debug with AI</a>
        </li>
          
        <li>
          <a href="/docs/copilot/guides/mcp-developer-guide">MCP Dev Guide</a>
        </li>
          
  </ul>
</li>
        
        <li>
          <a href="/docs/copilot/copilot-smart-actions">Smart Actions</a>
        </li>
          
        <li>
          <a href="/docs/copilot/copilot-tips-and-tricks">Tips and Tricks</a>
        </li>
          
        <li>
          <a href="/docs/copilot/security">Security</a>
        </li>
          
        <li>
          <a href="/docs/copilot/faq">FAQ</a>
        </li>
          
<li class="panel collapsed">
  <a class="area" role="button" href="#copilot-reference-articles" data-toggle="collapse" aria-expanded="false">Reference</a>
  <ul id="copilot-reference-articles" class="collapse " aria-expanded="false">

        <li>
          <a href="/docs/copilot/reference/copilot-vscode-features">Cheat Sheet</a>
        </li>
          
        <li>
          <a href="/docs/copilot/reference/copilot-settings">Settings Reference</a>
        </li>
          
        <li>
          <a href="/docs/copilot/reference/workspace-context">Workspace Context</a>
        </li>
          
  </ul>
</li>
        
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#sourcecontrol-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Source Control</a>
  <ul id="sourcecontrol-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/sourcecontrol/overview">Overview</a>
        </li>
          
        <li>
          <a href="/docs/sourcecontrol/intro-to-git">Introduction to Git</a>
        </li>
          
        <li>
          <a href="/docs/sourcecontrol/github">Collaborate on GitHub</a>
        </li>
          
        <li>
          <a href="/docs/sourcecontrol/faq">FAQ</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#terminal-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Terminal</a>
  <ul id="terminal-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/terminal/getting-started">Getting Started Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/terminal/basics">Terminal Basics</a>
        </li>
          
        <li>
          <a href="/docs/terminal/profiles">Terminal Profiles</a>
        </li>
          
        <li>
          <a href="/docs/terminal/shell-integration">Shell Integration</a>
        </li>
          
        <li>
          <a href="/docs/terminal/appearance">Appearance</a>
        </li>
          
        <li>
          <a href="/docs/terminal/advanced">Advanced</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#languages-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Languages</a>
  <ul id="languages-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/languages/overview">Overview</a>
        </li>
          
        <li>
          <a href="/docs/languages/javascript">JavaScript</a>
        </li>
          
        <li>
          <a href="/docs/languages/json">JSON</a>
        </li>
          
        <li>
          <a href="/docs/languages/html">HTML</a>
        </li>
          
        <li>
          <a href="/docs/languages/emmet">Emmet</a>
        </li>
          
        <li>
          <a href="/docs/languages/css">CSS, SCSS and Less</a>
        </li>
          
        <li>
          <a href="/docs/languages/typescript">TypeScript</a>
        </li>
          
        <li>
          <a href="/docs/languages/markdown">Markdown</a>
        </li>
          
        <li>
          <a href="/docs/languages/powershell">PowerShell</a>
        </li>
          
        <li>
          <a href="/docs/languages/cpp">C++</a>
        </li>
          
        <li>
          <a href="/docs/languages/java">Java</a>
        </li>
          
        <li>
          <a href="/docs/languages/php">PHP</a>
        </li>
          
        <li>
          <a href="/docs/languages/python">Python</a>
        </li>
          
        <li>
          <a href="/docs/languages/julia">Julia</a>
        </li>
          
        <li>
          <a href="/docs/languages/r">R</a>
        </li>
          
        <li>
          <a href="/docs/languages/ruby">Ruby</a>
        </li>
          
        <li>
          <a href="/docs/languages/rust">Rust</a>
        </li>
          
        <li>
          <a href="/docs/languages/go">Go</a>
        </li>
          
        <li>
          <a href="/docs/languages/tsql">T-SQL</a>
        </li>
          
        <li>
          <a href="/docs/languages/csharp">C#</a>
        </li>
          
        <li>
          <a href="/docs/languages/dotnet">.NET</a>
        </li>
          
        <li>
          <a href="/docs/languages/polyglot">Polyglot</a>
        </li>
          
        <li>
          <a href="/docs/languages/swift">Swift</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#nodejs-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Node.js / JavaScript</a>
  <ul id="nodejs-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/nodejs/working-with-javascript">Working with JavaScript</a>
        </li>
          
        <li>
          <a href="/docs/nodejs/nodejs-tutorial">Node.js Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/nodejs/nodejs-debugging">Node.js Debugging</a>
        </li>
          
        <li>
          <a href="/docs/nodejs/nodejs-deployment">Deploy Node.js Apps</a>
        </li>
          
        <li>
          <a href="/docs/nodejs/browser-debugging">Browser Debugging</a>
        </li>
          
        <li>
          <a href="/docs/nodejs/angular-tutorial">Angular Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/nodejs/reactjs-tutorial">React Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/nodejs/vuejs-tutorial">Vue Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/nodejs/debugging-recipes">Debugging Recipes</a>
        </li>
          
        <li>
          <a href="/docs/nodejs/profiling">Performance Profiling</a>
        </li>
          
        <li>
          <a href="/docs/nodejs/extensions">Extensions</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#typescript-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">TypeScript</a>
  <ul id="typescript-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/typescript/typescript-tutorial">Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/typescript/typescript-compiling">Compiling</a>
        </li>
          
        <li>
          <a href="/docs/typescript/typescript-editing">Editing</a>
        </li>
          
        <li>
          <a href="/docs/typescript/typescript-refactoring">Refactoring</a>
        </li>
          
        <li>
          <a href="/docs/typescript/typescript-debugging">Debugging</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#python-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Python</a>
  <ul id="python-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/python/python-quick-start">Quick Start</a>
        </li>
          
        <li>
          <a href="/docs/python/python-tutorial">Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/python/run">Run Python Code</a>
        </li>
          
        <li>
          <a href="/docs/python/editing">Editing</a>
        </li>
          
        <li>
          <a href="/docs/python/linting">Linting</a>
        </li>
          
        <li>
          <a href="/docs/python/formatting">Formatting</a>
        </li>
          
        <li>
          <a href="/docs/python/debugging">Debugging</a>
        </li>
          
        <li>
          <a href="/docs/python/environments">Environments</a>
        </li>
          
        <li>
          <a href="/docs/python/testing">Testing</a>
        </li>
          
        <li>
          <a href="/docs/python/jupyter-support-py">Python Interactive</a>
        </li>
          
        <li>
          <a href="/docs/python/tutorial-django">Django Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/python/tutorial-fastapi">FastAPI Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/python/tutorial-flask">Flask Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/python/tutorial-create-containers">Create Containers</a>
        </li>
          
        <li>
          <a href="/docs/python/python-on-azure">Deploy Python Apps</a>
        </li>
          
        <li>
          <a href="/docs/python/python-web">Python in the Web</a>
        </li>
          
        <li>
          <a href="/docs/python/settings-reference">Settings Reference</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#java-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Java</a>
  <ul id="java-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/java/java-tutorial">Getting Started</a>
        </li>
          
        <li>
          <a href="/docs/java/java-editing">Navigate and Edit</a>
        </li>
          
        <li>
          <a href="/docs/java/java-refactoring">Refactoring</a>
        </li>
          
        <li>
          <a href="/docs/java/java-linting">Formatting and Linting</a>
        </li>
          
        <li>
          <a href="/docs/java/java-project">Project Management</a>
        </li>
          
        <li>
          <a href="/docs/java/java-build">Build Tools</a>
        </li>
          
        <li>
          <a href="/docs/java/java-debugging">Run and Debug</a>
        </li>
          
        <li>
          <a href="/docs/java/java-testing">Testing</a>
        </li>
          
        <li>
          <a href="/docs/java/java-spring-boot">Spring Boot</a>
        </li>
          
        <li>
          <a href="/docs/java/java-tomcat-jetty">Application Servers</a>
        </li>
          
        <li>
          <a href="/docs/java/java-on-azure">Deploy Java Apps</a>
        </li>
          
        <li>
          <a href="/docs/java/java-gui">GUI Applications</a>
        </li>
          
        <li>
          <a href="/docs/java/extensions">Extensions</a>
        </li>
          
        <li>
          <a href="/docs/java/java-faq">FAQ</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#cpp-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">C++</a>
  <ul id="cpp-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/cpp/introvideos-cpp">Intro Videos</a>
        </li>
          
        <li>
          <a href="/docs/cpp/config-linux">GCC on Linux</a>
        </li>
          
        <li>
          <a href="/docs/cpp/config-mingw">GCC on Windows</a>
        </li>
          
        <li>
          <a href="/docs/cpp/config-wsl">GCC on Windows Subsystem for Linux</a>
        </li>
          
        <li>
          <a href="/docs/cpp/config-clang-mac">Clang on macOS</a>
        </li>
          
        <li>
          <a href="/docs/cpp/config-msvc">Microsoft C++ on Windows</a>
        </li>
          
        <li>
          <a href="/docs/cpp/build-with-cmake">Build with CMake</a>
        </li>
          
        <li>
          <a href="/docs/cpp/cmake-linux">CMake Tools on Linux</a>
        </li>
          
        <li>
          <a href="/docs/cpp/cmake-quickstart">CMake Quick Start</a>
        </li>
          
        <li>
          <a href="/docs/cpp/cpp-ide">Editing and Navigating</a>
        </li>
          
        <li>
          <a href="/docs/cpp/cpp-debug">Debugging</a>
        </li>
          
        <li>
          <a href="/docs/cpp/launch-json-reference">Configure Debugging</a>
        </li>
          
        <li>
          <a href="/docs/cpp/cpp-refactoring">Refactoring</a>
        </li>
          
        <li>
          <a href="/docs/cpp/customize-cpp-settings">Settings Reference</a>
        </li>
          
        <li>
          <a href="/docs/cpp/configure-intellisense">Configure IntelliSense</a>
        </li>
          
        <li>
          <a href="/docs/cpp/configure-intellisense-crosscompilation">Configure IntelliSense for Cross-Compiling</a>
        </li>
          
        <li>
          <a href="/docs/cpp/faq-cpp">FAQ</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#csharp-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">C#</a>
  <ul id="csharp-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/csharp/introvideos-csharp">Intro Videos</a>
        </li>
          
        <li>
          <a href="/docs/csharp/get-started">Get Started</a>
        </li>
          
        <li>
          <a href="/docs/csharp/navigate-edit">Navigate and Edit</a>
        </li>
          
        <li>
          <a href="/docs/csharp/intellicode">IntelliCode</a>
        </li>
          
        <li>
          <a href="/docs/csharp/refactoring">Refactoring</a>
        </li>
          
        <li>
          <a href="/docs/csharp/formatting-linting">Formatting and Linting</a>
        </li>
          
        <li>
          <a href="/docs/csharp/project-management">Project Management</a>
        </li>
          
        <li>
          <a href="/docs/csharp/build-tools">Build Tools</a>
        </li>
          
        <li>
          <a href="/docs/csharp/package-management">Package Management</a>
        </li>
          
        <li>
          <a href="/docs/csharp/debugging">Run and Debug</a>
        </li>
          
        <li>
          <a href="/docs/csharp/testing">Testing</a>
        </li>
          
        <li>
          <a href="/docs/csharp/cs-dev-kit-faq">FAQ</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#containers-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Container Tools</a>
  <ul id="containers-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/containers/overview">Overview</a>
        </li>
          
        <li>
          <a href="/docs/containers/quickstart-node">Node.js</a>
        </li>
          
        <li>
          <a href="/docs/containers/quickstart-python">Python</a>
        </li>
          
        <li>
          <a href="/docs/containers/quickstart-aspnet-core">ASP.NET Core</a>
        </li>
          
        <li>
          <a href="/docs/containers/debug-common">Debug</a>
        </li>
          
        <li>
          <a href="/docs/containers/docker-compose">Docker Compose</a>
        </li>
          
        <li>
          <a href="/docs/containers/quickstart-container-registries">Registries</a>
        </li>
          
        <li>
          <a href="/docs/containers/app-service">Deploy to Azure</a>
        </li>
          
        <li>
          <a href="/docs/containers/choosing-dev-environment">Choose a Dev Environment</a>
        </li>
          
        <li>
          <a href="/docs/containers/reference">Customize</a>
        </li>
          
        <li>
          <a href="/docs/containers/bridge-to-kubernetes">Develop with Kubernetes</a>
        </li>
          
        <li>
          <a href="/docs/containers/troubleshooting">Tips and Tricks</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#datascience-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Data Science</a>
  <ul id="datascience-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/datascience/overview">Overview</a>
        </li>
          
        <li>
          <a href="/docs/datascience/jupyter-notebooks">Jupyter Notebooks</a>
        </li>
          
        <li>
          <a href="/docs/datascience/data-science-tutorial">Data Science Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/datascience/python-interactive">Python Interactive</a>
        </li>
          
        <li>
          <a href="/docs/datascience/data-wrangler-quick-start">Data Wrangler Quick Start</a>
        </li>
          
        <li>
          <a href="/docs/datascience/data-wrangler">Data Wrangler</a>
        </li>
          
        <li>
          <a href="/docs/datascience/pytorch-support">PyTorch Support</a>
        </li>
          
        <li>
          <a href="/docs/datascience/azure-machine-learning">Azure Machine Learning</a>
        </li>
          
        <li>
          <a href="/docs/datascience/jupyter-kernel-management">Manage Jupyter Kernels</a>
        </li>
          
        <li>
          <a href="/docs/datascience/notebooks-web">Jupyter Notebooks on the Web</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#intelligentapps-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Intelligent Apps</a>
  <ul id="intelligentapps-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/intelligentapps/overview">AI Toolkit Overview</a>
        </li>
          
        <li>
          <a href="/docs/intelligentapps/models">Models</a>
        </li>
          
        <li>
          <a href="/docs/intelligentapps/playground">Playground</a>
        </li>
          
        <li>
          <a href="/docs/intelligentapps/agentbuilder">Agent Builder</a>
        </li>
          
        <li>
          <a href="/docs/intelligentapps/bulkrun">Bulk Run</a>
        </li>
          
        <li>
          <a href="/docs/intelligentapps/evaluation">Evaluation</a>
        </li>
          
        <li>
          <a href="/docs/intelligentapps/finetune">Fine-tune</a>
        </li>
          
        <li>
          <a href="/docs/intelligentapps/modelconversion">Model Conversion</a>
        </li>
          
        <li>
          <a href="/docs/intelligentapps/tracing">Tracing</a>
        </li>
          
        <li>
          <a href="/docs/intelligentapps/faq">FAQ</a>
        </li>
          
<li class="panel collapsed">
  <a class="area" role="button" href="#intelligentapps-reference-articles" data-toggle="collapse" aria-expanded="false">Reference</a>
  <ul id="intelligentapps-reference-articles" class="collapse " aria-expanded="false">

        <li>
          <a href="/docs/intelligentapps/reference/FileStructure">File Structure</a>
        </li>
          
        <li>
          <a href="/docs/intelligentapps/reference/ManualModelConversion">Manual Model Conversion</a>
        </li>
          
        <li>
          <a href="/docs/intelligentapps/reference/ManualConversionOnGPU">Manual Model Conversion On GPU</a>
        </li>
          
        <li>
          <a href="/docs/intelligentapps/reference/SetupWithoutAITK">Setup Environment Without AI Toolkit</a>
        </li>
          
        <li>
          <a href="/docs/intelligentapps/reference/TemplateProject">Template Project</a>
        </li>
          
  </ul>
</li>
        
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#azure-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Azure</a>
  <ul id="azure-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/azure/overview">Overview</a>
        </li>
          
        <li>
          <a href="/docs/azure/gettingstarted">Getting Started</a>
        </li>
          
        <li>
          <a href="/docs/azure/resourcesextension">Resources View</a>
        </li>
          
        <li>
          <a href="/docs/azure/deployment">Deployment</a>
        </li>
          
        <li>
          <a href="/docs/azure/vscodeforweb">VS Code for the Web - Azure</a>
        </li>
          
        <li>
          <a href="/docs/azure/containers">Containers</a>
        </li>
          
        <li>
          <a href="/docs/azure/aksextensions">Azure Kubernetes Service</a>
        </li>
          
        <li>
          <a href="/docs/azure/kubernetes">Kubernetes</a>
        </li>
          
        <li>
          <a href="/docs/azure/mongodb">MongoDB</a>
        </li>
          
        <li>
          <a href="/docs/azure/remote-debugging">Remote Debugging for Node.js</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#remote-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Remote</a>
  <ul id="remote-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/remote/remote-overview">Overview</a>
        </li>
          
        <li>
          <a href="/docs/remote/ssh">SSH</a>
        </li>
          
        <li>
          <a href="/docs/remote/dev-containers">Dev Containers</a>
        </li>
          
        <li>
          <a href="/docs/remote/wsl">Windows Subsystem for Linux</a>
        </li>
          
        <li>
          <a href="/docs/remote/codespaces">GitHub Codespaces</a>
        </li>
          
        <li>
          <a href="/docs/remote/vscode-server">VS Code Server</a>
        </li>
          
        <li>
          <a href="/docs/remote/tunnels">Tunnels</a>
        </li>
          
        <li>
          <a href="/docs/remote/ssh-tutorial">SSH Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/remote/wsl-tutorial">WSL Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/remote/troubleshooting">Tips and Tricks</a>
        </li>
          
        <li>
          <a href="/docs/remote/faq">FAQ</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#devcontainers-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Dev Containers</a>
  <ul id="devcontainers-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/devcontainers/containers">Overview</a>
        </li>
          
        <li>
          <a href="/docs/devcontainers/tutorial">Tutorial</a>
        </li>
          
        <li>
          <a href="/docs/devcontainers/attach-container">Attach to Container</a>
        </li>
          
        <li>
          <a href="/docs/devcontainers/create-dev-container">Create Dev Container</a>
        </li>
          
        <li>
          <a href="/docs/devcontainers/containers-advanced">Advanced Containers</a>
        </li>
          
        <li>
          <a href="/docs/devcontainers/devcontainerjson-reference">devcontainer.json</a>
        </li>
          
        <li>
          <a href="/docs/devcontainers/devcontainer-cli">Dev Container CLI</a>
        </li>
          
        <li>
          <a href="/docs/devcontainers/tips-and-tricks">Tips and Tricks</a>
        </li>
          
        <li>
          <a href="/docs/devcontainers/faq">FAQ</a>
        </li>
          
  </ul>
</li>
    
<li class="panel ">
  <a class="area" role="button" href="#reference-articles" data-parent="#main-nav" data-toggle="collapse" aria-expanded="true">Reference</a>
  <ul id="reference-articles" class="collapse " aria-expanded="true">

        <li>
          <a href="/docs/reference/default-keybindings">Default Keyboard Shortcuts</a>
        </li>
          
        <li>
          <a href="/docs/reference/default-settings">Default Settings</a>
        </li>
          
        <li>
          <a href="/docs/reference/variables-reference">Substitution Variables</a>
        </li>
          
        <li>
          <a href="/docs/reference/tasks-appendix">Tasks Schema</a>
        </li>
          
  </ul>
</li>
    
  </ul>
</nav>

<nav id="small-nav" aria-label="Topics" class="docs-nav hidden-md hidden-lg">
  <label class="faux-h4" for="small-nav-dropdown">Topics</label>
  <select id="small-nav-dropdown" aria-label="topics">
    <option value="/docs">Overview</option>

  <optgroup label="Setup">

        <option value="/docs/setup/setup-overview">Overview</option>
        
        <option value="/docs/setup/linux">Linux</option>
        
        <option value="/docs/setup/mac">macOS</option>
        
        <option value="/docs/setup/windows">Windows</option>
        
        <option value="/docs/setup/vscode-web">VS Code for the Web</option>
        
        <option value="/docs/setup/raspberry-pi">Raspberry Pi</option>
        
        <option value="/docs/setup/network">Network</option>
        
        <option value="/docs/setup/additional-components">Additional Components</option>
        
        <option value="/docs/setup/enterprise">Enterprise</option>
        
        <option value="/docs/setup/uninstall">Uninstall</option>
        
  </optgroup>
  
  <optgroup label="Get Started">

        <option value="/docs/getstarted/getting-started">VS Code Tutorial</option>
        
        <option value="/docs/getstarted/copilot-quickstart">Copilot Quickstart</option>
        
        <option value="/docs/getstarted/userinterface">User Interface</option>
        
        <option value="/docs/getstarted/personalize-vscode">Personalize VS Code</option>
        
        <option value="/docs/getstarted/extensions">Install Extensions</option>
        
        <option value="/docs/getstarted/tips-and-tricks">Tips and Tricks</option>
        
        <option value="/docs/getstarted/introvideos">Intro Videos</option>
        
  </optgroup>
  
  <optgroup label="Configure">

        <option value="/docs/configure/locales">Display Language</option>
        
        <option value="/docs/configure/custom-layout">Layout</option>
        
        <option value="/docs/configure/keybindings">Keyboard Shortcuts</option>
        
        <option value="/docs/configure/settings">Settings</option>
        
        <option value="/docs/configure/settings-sync">Settings Sync</option>
        
        </optgroup><optgroup label="Configure - Extensions">

          <option value="/docs/configure/extensions/extension-marketplace">Extension Marketplace</option>
          
          <option value="/docs/configure/extensions/extension-runtime-security">Extension Runtime Security</option>
          
        </optgroup>

        <option value="/docs/configure/themes">Themes</option>
        
        <option value="/docs/configure/profiles">Profiles</option>
        
        <optgroup label="Configure - Accessibility">

          <option value="/docs/configure/accessibility/accessibility">Overview</option>
          
          <option value="/docs/configure/accessibility/voice">Voice Interactions</option>
          
        </optgroup>

        <option value="/docs/configure/command-line">Command Line Interface</option>
        
        <option value="/docs/configure/telemetry">Telemetry</option>
        
  
  
  <optgroup label="Edit code">

        <option value="/docs/editing/codebasics">Basic Editing</option>
        
        <option value="/docs/editing/intellisense">IntelliSense</option>
        
        <option value="/docs/editing/editingevolved">Code Navigation</option>
        
        <option value="/docs/editing/refactoring">Refactoring</option>
        
        <option value="/docs/editing/userdefinedsnippets">Snippets</option>
        
        </optgroup><optgroup label="Edit code - Workspaces">

          <option value="/docs/editing/workspaces/workspaces">Overview</option>
          
          <option value="/docs/editing/workspaces/multi-root-workspaces">Multi-root Workspaces</option>
          
          <option value="/docs/editing/workspaces/workspace-trust">Workspace Trust</option>
          
        </optgroup>

  
  
  <optgroup label="Build, Debug, Test">

        <option value="/docs/debugtest/tasks">Tasks</option>
        
        <option value="/docs/debugtest/debugging">Debugging</option>
        
        <option value="/docs/debugtest/debugging-configuration">Debug Configuration</option>
        
        <option value="/docs/debugtest/testing">Testing</option>
        
        <option value="/docs/debugtest/port-forwarding">Port Forwarding</option>
        
  </optgroup>
  
  <optgroup label="GitHub Copilot">

        <option value="/docs/copilot/overview">Overview</option>
        
        <option value="/docs/copilot/setup">Setup</option>
        
        <option value="/docs/copilot/getting-started">Quickstart</option>
        
        </optgroup><optgroup label="GitHub Copilot - Chat">

          <option value="/docs/copilot/chat/copilot-chat">Chat Overview</option>
          
          <option value="/docs/copilot/chat/copilot-chat-context">Manage Context</option>
          
          <option value="/docs/copilot/chat/chat-ask-mode">Ask Mode</option>
          
          <option value="/docs/copilot/chat/copilot-edits">Edit Mode</option>
          
          <option value="/docs/copilot/chat/chat-agent-mode">Agent Mode</option>
          
          <option value="/docs/copilot/chat/inline-chat">Inline Chat</option>
          
          <option value="/docs/copilot/chat/prompt-crafting">Prompt Engineering</option>
          
        </optgroup>

        <option value="/docs/copilot/ai-powered-suggestions">Code Completions</option>
        
        <option value="/docs/copilot/copilot-coding-agent">Copilot Coding Agent</option>
        
        <optgroup label="GitHub Copilot - Customize Copilot">

          <option value="/docs/copilot/customization/overview">Overview</option>
          
          <option value="/docs/copilot/customization/custom-instructions">Custom Instructions</option>
          
          <option value="/docs/copilot/customization/prompt-files">Prompt Files</option>
          
          <option value="/docs/copilot/customization/custom-chat-modes">Chat Modes</option>
          
          <option value="/docs/copilot/customization/language-models">Language Models</option>
          
          <option value="/docs/copilot/customization/mcp-servers">MCP</option>
          
        </optgroup>

        <optgroup label="GitHub Copilot - Guides">

          <option value="/docs/copilot/guides/notebooks-with-ai">Edit Notebooks with AI</option>
          
          <option value="/docs/copilot/guides/test-with-copilot">Test with AI</option>
          
          <option value="/docs/copilot/guides/debug-with-copilot">Debug with AI</option>
          
          <option value="/docs/copilot/guides/mcp-developer-guide">MCP Dev Guide</option>
          
        </optgroup>

        <option value="/docs/copilot/copilot-smart-actions">Smart Actions</option>
        
        <option value="/docs/copilot/copilot-tips-and-tricks">Tips and Tricks</option>
        
        <option value="/docs/copilot/security">Security</option>
        
        <option value="/docs/copilot/faq">FAQ</option>
        
        <optgroup label="GitHub Copilot - Reference">

          <option value="/docs/copilot/reference/copilot-vscode-features">Cheat Sheet</option>
          
          <option value="/docs/copilot/reference/copilot-settings">Settings Reference</option>
          
          <option value="/docs/copilot/reference/workspace-context">Workspace Context</option>
          
        </optgroup>

  
  
  <optgroup label="Source Control">

        <option value="/docs/sourcecontrol/overview">Overview</option>
        
        <option value="/docs/sourcecontrol/intro-to-git">Introduction to Git</option>
        
        <option value="/docs/sourcecontrol/github">Collaborate on GitHub</option>
        
        <option value="/docs/sourcecontrol/faq">FAQ</option>
        
  </optgroup>
  
  <optgroup label="Terminal">

        <option value="/docs/terminal/getting-started">Getting Started Tutorial</option>
        
        <option value="/docs/terminal/basics">Terminal Basics</option>
        
        <option value="/docs/terminal/profiles">Terminal Profiles</option>
        
        <option value="/docs/terminal/shell-integration">Shell Integration</option>
        
        <option value="/docs/terminal/appearance">Appearance</option>
        
        <option value="/docs/terminal/advanced">Advanced</option>
        
  </optgroup>
  
  <optgroup label="Languages">

        <option value="/docs/languages/overview">Overview</option>
        
        <option value="/docs/languages/javascript">JavaScript</option>
        
        <option value="/docs/languages/json">JSON</option>
        
        <option value="/docs/languages/html">HTML</option>
        
        <option value="/docs/languages/emmet">Emmet</option>
        
        <option value="/docs/languages/css">CSS, SCSS and Less</option>
        
        <option value="/docs/languages/typescript">TypeScript</option>
        
        <option value="/docs/languages/markdown">Markdown</option>
        
        <option value="/docs/languages/powershell">PowerShell</option>
        
        <option value="/docs/languages/cpp">C++</option>
        
        <option value="/docs/languages/java">Java</option>
        
        <option value="/docs/languages/php">PHP</option>
        
        <option value="/docs/languages/python">Python</option>
        
        <option value="/docs/languages/julia">Julia</option>
        
        <option value="/docs/languages/r">R</option>
        
        <option value="/docs/languages/ruby">Ruby</option>
        
        <option value="/docs/languages/rust">Rust</option>
        
        <option value="/docs/languages/go">Go</option>
        
        <option value="/docs/languages/tsql">T-SQL</option>
        
        <option value="/docs/languages/csharp">C#</option>
        
        <option value="/docs/languages/dotnet">.NET</option>
        
        <option value="/docs/languages/polyglot">Polyglot</option>
        
        <option value="/docs/languages/swift">Swift</option>
        
  </optgroup>
  
  <optgroup label="Node.js / JavaScript">

        <option value="/docs/nodejs/working-with-javascript">Working with JavaScript</option>
        
        <option value="/docs/nodejs/nodejs-tutorial">Node.js Tutorial</option>
        
        <option value="/docs/nodejs/nodejs-debugging">Node.js Debugging</option>
        
        <option value="/docs/nodejs/nodejs-deployment">Deploy Node.js Apps</option>
        
        <option value="/docs/nodejs/browser-debugging">Browser Debugging</option>
        
        <option value="/docs/nodejs/angular-tutorial">Angular Tutorial</option>
        
        <option value="/docs/nodejs/reactjs-tutorial">React Tutorial</option>
        
        <option value="/docs/nodejs/vuejs-tutorial">Vue Tutorial</option>
        
        <option value="/docs/nodejs/debugging-recipes">Debugging Recipes</option>
        
        <option value="/docs/nodejs/profiling">Performance Profiling</option>
        
        <option value="/docs/nodejs/extensions">Extensions</option>
        
  </optgroup>
  
  <optgroup label="TypeScript">

        <option value="/docs/typescript/typescript-tutorial">Tutorial</option>
        
        <option value="/docs/typescript/typescript-compiling">Compiling</option>
        
        <option value="/docs/typescript/typescript-editing">Editing</option>
        
        <option value="/docs/typescript/typescript-refactoring">Refactoring</option>
        
        <option value="/docs/typescript/typescript-debugging">Debugging</option>
        
  </optgroup>
  
  <optgroup label="Python">

        <option value="/docs/python/python-quick-start">Quick Start</option>
        
        <option value="/docs/python/python-tutorial">Tutorial</option>
        
        <option value="/docs/python/run">Run Python Code</option>
        
        <option value="/docs/python/editing">Editing</option>
        
        <option value="/docs/python/linting">Linting</option>
        
        <option value="/docs/python/formatting">Formatting</option>
        
        <option value="/docs/python/debugging">Debugging</option>
        
        <option value="/docs/python/environments">Environments</option>
        
        <option value="/docs/python/testing">Testing</option>
        
        <option value="/docs/python/jupyter-support-py">Python Interactive</option>
        
        <option value="/docs/python/tutorial-django">Django Tutorial</option>
        
        <option value="/docs/python/tutorial-fastapi">FastAPI Tutorial</option>
        
        <option value="/docs/python/tutorial-flask">Flask Tutorial</option>
        
        <option value="/docs/python/tutorial-create-containers">Create Containers</option>
        
        <option value="/docs/python/python-on-azure">Deploy Python Apps</option>
        
        <option value="/docs/python/python-web">Python in the Web</option>
        
        <option value="/docs/python/settings-reference">Settings Reference</option>
        
  </optgroup>
  
  <optgroup label="Java">

        <option value="/docs/java/java-tutorial">Getting Started</option>
        
        <option value="/docs/java/java-editing">Navigate and Edit</option>
        
        <option value="/docs/java/java-refactoring">Refactoring</option>
        
        <option value="/docs/java/java-linting">Formatting and Linting</option>
        
        <option value="/docs/java/java-project">Project Management</option>
        
        <option value="/docs/java/java-build">Build Tools</option>
        
        <option value="/docs/java/java-debugging">Run and Debug</option>
        
        <option value="/docs/java/java-testing">Testing</option>
        
        <option value="/docs/java/java-spring-boot">Spring Boot</option>
        
        <option value="/docs/java/java-tomcat-jetty">Application Servers</option>
        
        <option value="/docs/java/java-on-azure">Deploy Java Apps</option>
        
        <option value="/docs/java/java-gui">GUI Applications</option>
        
        <option value="/docs/java/extensions">Extensions</option>
        
        <option value="/docs/java/java-faq">FAQ</option>
        
  </optgroup>
  
  <optgroup label="C++">

        <option value="/docs/cpp/introvideos-cpp">Intro Videos</option>
        
        <option value="/docs/cpp/config-linux">GCC on Linux</option>
        
        <option value="/docs/cpp/config-mingw">GCC on Windows</option>
        
        <option value="/docs/cpp/config-wsl">GCC on Windows Subsystem for Linux</option>
        
        <option value="/docs/cpp/config-clang-mac">Clang on macOS</option>
        
        <option value="/docs/cpp/config-msvc">Microsoft C++ on Windows</option>
        
        <option value="/docs/cpp/build-with-cmake">Build with CMake</option>
        
        <option value="/docs/cpp/cmake-linux">CMake Tools on Linux</option>
        
        <option value="/docs/cpp/cmake-quickstart">CMake Quick Start</option>
        
        <option value="/docs/cpp/cpp-ide">Editing and Navigating</option>
        
        <option value="/docs/cpp/cpp-debug">Debugging</option>
        
        <option value="/docs/cpp/launch-json-reference">Configure Debugging</option>
        
        <option value="/docs/cpp/cpp-refactoring">Refactoring</option>
        
        <option value="/docs/cpp/customize-cpp-settings">Settings Reference</option>
        
        <option value="/docs/cpp/configure-intellisense">Configure IntelliSense</option>
        
        <option value="/docs/cpp/configure-intellisense-crosscompilation">Configure IntelliSense for Cross-Compiling</option>
        
        <option value="/docs/cpp/faq-cpp">FAQ</option>
        
  </optgroup>
  
  <optgroup label="C#">

        <option value="/docs/csharp/introvideos-csharp">Intro Videos</option>
        
        <option value="/docs/csharp/get-started">Get Started</option>
        
        <option value="/docs/csharp/navigate-edit">Navigate and Edit</option>
        
        <option value="/docs/csharp/intellicode">IntelliCode</option>
        
        <option value="/docs/csharp/refactoring">Refactoring</option>
        
        <option value="/docs/csharp/formatting-linting">Formatting and Linting</option>
        
        <option value="/docs/csharp/project-management">Project Management</option>
        
        <option value="/docs/csharp/build-tools">Build Tools</option>
        
        <option value="/docs/csharp/package-management">Package Management</option>
        
        <option value="/docs/csharp/debugging">Run and Debug</option>
        
        <option value="/docs/csharp/testing">Testing</option>
        
        <option value="/docs/csharp/cs-dev-kit-faq">FAQ</option>
        
  </optgroup>
  
  <optgroup label="Container Tools">

        <option value="/docs/containers/overview">Overview</option>
        
        <option value="/docs/containers/quickstart-node">Node.js</option>
        
        <option value="/docs/containers/quickstart-python">Python</option>
        
        <option value="/docs/containers/quickstart-aspnet-core">ASP.NET Core</option>
        
        <option value="/docs/containers/debug-common">Debug</option>
        
        <option value="/docs/containers/docker-compose">Docker Compose</option>
        
        <option value="/docs/containers/quickstart-container-registries">Registries</option>
        
        <option value="/docs/containers/app-service">Deploy to Azure</option>
        
        <option value="/docs/containers/choosing-dev-environment">Choose a Dev Environment</option>
        
        <option value="/docs/containers/reference">Customize</option>
        
        <option value="/docs/containers/bridge-to-kubernetes">Develop with Kubernetes</option>
        
        <option value="/docs/containers/troubleshooting">Tips and Tricks</option>
        
  </optgroup>
  
  <optgroup label="Data Science">

        <option value="/docs/datascience/overview">Overview</option>
        
        <option value="/docs/datascience/jupyter-notebooks">Jupyter Notebooks</option>
        
        <option value="/docs/datascience/data-science-tutorial">Data Science Tutorial</option>
        
        <option value="/docs/datascience/python-interactive">Python Interactive</option>
        
        <option value="/docs/datascience/data-wrangler-quick-start">Data Wrangler Quick Start</option>
        
        <option value="/docs/datascience/data-wrangler">Data Wrangler</option>
        
        <option value="/docs/datascience/pytorch-support">PyTorch Support</option>
        
        <option value="/docs/datascience/azure-machine-learning">Azure Machine Learning</option>
        
        <option value="/docs/datascience/jupyter-kernel-management">Manage Jupyter Kernels</option>
        
        <option value="/docs/datascience/notebooks-web">Jupyter Notebooks on the Web</option>
        
  </optgroup>
  
  <optgroup label="Intelligent Apps">

        <option value="/docs/intelligentapps/overview">AI Toolkit Overview</option>
        
        <option value="/docs/intelligentapps/models">Models</option>
        
        <option value="/docs/intelligentapps/playground">Playground</option>
        
        <option value="/docs/intelligentapps/agentbuilder">Agent Builder</option>
        
        <option value="/docs/intelligentapps/bulkrun">Bulk Run</option>
        
        <option value="/docs/intelligentapps/evaluation">Evaluation</option>
        
        <option value="/docs/intelligentapps/finetune">Fine-tune</option>
        
        <option value="/docs/intelligentapps/modelconversion">Model Conversion</option>
        
        <option value="/docs/intelligentapps/tracing">Tracing</option>
        
        <option value="/docs/intelligentapps/faq">FAQ</option>
        
        </optgroup><optgroup label="Intelligent Apps - Reference">

          <option value="/docs/intelligentapps/reference/FileStructure">File Structure</option>
          
          <option value="/docs/intelligentapps/reference/ManualModelConversion">Manual Model Conversion</option>
          
          <option value="/docs/intelligentapps/reference/ManualConversionOnGPU">Manual Model Conversion On GPU</option>
          
          <option value="/docs/intelligentapps/reference/SetupWithoutAITK">Setup Environment Without AI Toolkit</option>
          
          <option value="/docs/intelligentapps/reference/TemplateProject">Template Project</option>
          
        </optgroup>

  
  
  <optgroup label="Azure">

        <option value="/docs/azure/overview">Overview</option>
        
        <option value="/docs/azure/gettingstarted">Getting Started</option>
        
        <option value="/docs/azure/resourcesextension">Resources View</option>
        
        <option value="/docs/azure/deployment">Deployment</option>
        
        <option value="/docs/azure/vscodeforweb">VS Code for the Web - Azure</option>
        
        <option value="/docs/azure/containers">Containers</option>
        
        <option value="/docs/azure/aksextensions">Azure Kubernetes Service</option>
        
        <option value="/docs/azure/kubernetes">Kubernetes</option>
        
        <option value="/docs/azure/mongodb">MongoDB</option>
        
        <option value="/docs/azure/remote-debugging">Remote Debugging for Node.js</option>
        
  </optgroup>
  
  <optgroup label="Remote">

        <option value="/docs/remote/remote-overview">Overview</option>
        
        <option value="/docs/remote/ssh">SSH</option>
        
        <option value="/docs/remote/dev-containers">Dev Containers</option>
        
        <option value="/docs/remote/wsl">Windows Subsystem for Linux</option>
        
        <option value="/docs/remote/codespaces">GitHub Codespaces</option>
        
        <option value="/docs/remote/vscode-server">VS Code Server</option>
        
        <option value="/docs/remote/tunnels">Tunnels</option>
        
        <option value="/docs/remote/ssh-tutorial">SSH Tutorial</option>
        
        <option value="/docs/remote/wsl-tutorial">WSL Tutorial</option>
        
        <option value="/docs/remote/troubleshooting">Tips and Tricks</option>
        
        <option value="/docs/remote/faq">FAQ</option>
        
  </optgroup>
  
  <optgroup label="Dev Containers">

        <option value="/docs/devcontainers/containers">Overview</option>
        
        <option value="/docs/devcontainers/tutorial">Tutorial</option>
        
        <option value="/docs/devcontainers/attach-container">Attach to Container</option>
        
        <option value="/docs/devcontainers/create-dev-container">Create Dev Container</option>
        
        <option value="/docs/devcontainers/containers-advanced">Advanced Containers</option>
        
        <option value="/docs/devcontainers/devcontainerjson-reference">devcontainer.json</option>
        
        <option value="/docs/devcontainers/devcontainer-cli">Dev Container CLI</option>
        
        <option value="/docs/devcontainers/tips-and-tricks">Tips and Tricks</option>
        
        <option value="/docs/devcontainers/faq">FAQ</option>
        
  </optgroup>
  
  <optgroup label="Reference">

        <option value="/docs/reference/default-keybindings">Default Keyboard Shortcuts</option>
        
        <option value="/docs/reference/default-settings">Default Settings</option>
        
        <option value="/docs/reference/variables-reference">Substitution Variables</option>
        
        <option value="/docs/reference/tasks-appendix">Tasks Schema</option>
        
  </optgroup>
  
  </select>
</nav> </div>
		<div class="col-xs-10 col-md-10">
			<div id="confirmation" style="display: block;">
				<p>
				</p><h2>Thanks for downloading VS Code!</h2>
				<p class="thanks">Download not starting? Try this <a href="/sha/download?build=stable&amp;os=win32-x64-user" id="direct-link">direct download link.</a>
				</p>
				<p></p>
				<div id="confirmation-video">
					<h3>Want a head start? Watch this 5min overview.</h3>
					<p>
						<iframe src="https://www.microsoft.com/en-us/videoplayer/embed/RE4M6Vx" width="640" height="320" allowfullscreen="true" frameborder="0"></iframe>
						Continue with <a href="/docs/introvideos/configure"><em>Customize VS Code</em></a> or browse <a href="/docs/getstarted/introvideos">all intro videos</a>.
					</p>
				</div>
			</div>

			<div>
				<h1>Visual Studio Code documentation</h1>
					<p>Get familiar with Visual Studio Code and learn how to code faster with AI.</p>
			</div>

			<div>
				<h2 id="getting-started">Getting started</h2>

				<div class="row">
					<div class="feature-grid col-sm-12">
						<a id="download-card" href="/download" class="feature-card" style="display: none;">
							<i class="codicon codicon-tools"></i>
							<h3 class="feature-card-title">Download Visual Studio Code</h3>
							<p>Download VS Code for Windows, macOS, or Linux.</p>
						</a>

						<a id="setup-card" href="/docs/setup/setup-overview" class="feature-card" style="display: inline;">
							<i class="codicon codicon-tools"></i>
							<h3 class="feature-card-title">Set up Visual Studio Code</h3>
							<p>Follow the setup guide to install and configure VS Code for your OS.</p>
						</a>

						<a href="/docs/getstarted/getting-started" class="feature-card">
							<i class="codicon codicon-rocket"></i>
							<h3 class="feature-card-title">Getting started</h3>
							<p>Discover the key features of VS Code with the step-by-step tutorial.</p>
						</a>

						<a href="/docs/copilot/getting-started" class="feature-card">
							<i class="codicon codicon-copilot"></i>
							<h3 class="feature-card-title">Code faster with AI</h3>
							<p>Get started with GitHub Copilot, your AI coding assistant.</p>
						</a>
					</div>
				</div>
			</div>

			<div>
				<h2 id="features">Code with rich features</h2>

				<div class="row">
					<div class="feature-grid col-sm-12">

						<a href="/docs/languages/overview" class="feature-card">
							<i class="codicon codicon-file-code"></i>
							<h3 class="feature-card-title">Code in any language</h3>
							<p>Write code in your favorite programming language.</p>
						</a>

						<a href="/docs/sourcecontrol/overview" class="feature-card">
							<i class="codicon codicon-source-control"></i>
							<h3 class="feature-card-title">Version control</h3>
							<p>Built-in support for git and many other source control providers.</p>
						</a>

						<a href="/docs/editor/debugging" class="feature-card">
							<i class="codicon codicon-debug"></i>
							<h3 class="feature-card-title">Debugging</h3>
							<p>Debug your code without leaving your editor.</p>
						</a>

						<a href="/docs/editor/testing" class="feature-card">
							<i class="codicon codicon-beaker"></i>
							<h3 class="feature-card-title">Testing</h3>
							<p>Run automated tests and view test coverage to validate your code.</p>
						</a>

						<a href="/docs/remote/remote-overview" class="feature-card">
							<i class="codicon codicon-remote"></i>
							<h3 class="feature-card-title">Code anywhere</h3>
							<p>Use a container, remote machine, or WSL as your development environment.</p>
						</a>

						<a href="/docs/getstarted/introvideos" class="feature-card">
							<i class="codicon codicon-device-camera-video"></i>
							<h3 class="feature-card-title">Videos</h3>
							<p>Watch the introduction videos to learn more.</p>
						</a>
					</div>
				</div>
			</div>

			<div>
				<h2 id="top-extensions">Top Extensions</h2>
					<p>Enable additional languages, themes, debuggers, commands, and more. VS Code's growing community shares their
						secret sauce to improve your workflow.</p>
				<div class="marketplace-extensions-top"><div><div class="extensions"><div class="gallery-items"><a aria-label="Python extension" aria-describedby="cover-f1f59ae4-9318-4f3c-a9b5-81b2eaa5f8a5 details-f1f59ae4-9318-4f3c-a9b5-81b2eaa5f8a5" class="gallery-item-card-container" href="https://marketplace.visualstudio.com/items?itemName=ms-python.python" target="_blank" rel="noopener noreferrer"><div class="gallery-item-card"><div class="cover" id="cover-f1f59ae4-9318-4f3c-a9b5-81b2eaa5f8a5" aria-label="Published by ms-python. 182.2M installs."><div class="icon-cell"><img class="icon" src="https://ms-python.gallerycdn.vsassets.io/extensions/ms-python/python/2025.13.2025090201/1756809778264/Microsoft.VisualStudio.Services.Icons.Default" alt="Python"></div><div class="core-info-cell"><div class="name" title="Python"><span>Python</span></div><div class="core-info-second-row"><span class="installs"><span class="install-icon"></span><span class="install-count">182.2M</span></span><div class="publisher"><span>ms-python</span></div></div></div></div></div></a><a aria-label="C/C++ extension" aria-describedby="cover-690b692e-e8a9-493f-b802-8089d50ac1b2 details-690b692e-e8a9-493f-b802-8089d50ac1b2" class="gallery-item-card-container" href="https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools" target="_blank" rel="noopener noreferrer"><div class="gallery-item-card"><div class="cover" id="cover-690b692e-e8a9-493f-b802-8089d50ac1b2" aria-label="Published by ms-vscode. 86.9M installs."><div class="icon-cell"><img class="icon" src="https://ms-vscode.gallerycdn.vsassets.io/extensions/ms-vscode/cpptools/1.27.3/1756945108184/Microsoft.VisualStudio.Services.Icons.Default" alt="C/C++"></div><div class="core-info-cell"><div class="name" title="C/C++"><span>C/C++</span></div><div class="core-info-second-row"><span class="installs"><span class="install-icon"></span><span class="install-count">86.9M</span></span><div class="publisher"><span>ms-vscode</span></div></div></div></div></div></a><a aria-label="GitHub Copilot extension" aria-describedby="cover-23c4aeee-f844-43cd-b53e-1113e483f1a6 details-23c4aeee-f844-43cd-b53e-1113e483f1a6" class="gallery-item-card-container" href="https://marketplace.visualstudio.com/items?itemName=GitHub.copilot" target="_blank" rel="noopener noreferrer"><div class="gallery-item-card"><div class="cover" id="cover-23c4aeee-f844-43cd-b53e-1113e483f1a6" aria-label="Published by GitHub. 49.6M installs."><div class="icon-cell"><img class="icon" src="https://GitHub.gallerycdn.vsassets.io/extensions/github/copilot/1.367.1777/1757001274753/Microsoft.VisualStudio.Services.Icons.Default" alt="GitHub Copilot"></div><div class="core-info-cell"><div class="name" title="GitHub Copilot"><span>GitHub Copilot</span></div><div class="core-info-second-row"><span class="installs"><span class="install-icon"></span><span class="install-count">49.6M</span></span><div class="publisher"><span>GitHub</span></div></div></div></div></div></a><a aria-label="Extension Pack for Java extension" aria-describedby="cover-96f11e1f-1a46-4592-b084-f025b2c2a81f details-96f11e1f-1a46-4592-b084-f025b2c2a81f" class="gallery-item-card-container" href="https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack" target="_blank" rel="noopener noreferrer"><div class="gallery-item-card"><div class="cover" id="cover-96f11e1f-1a46-4592-b084-f025b2c2a81f" aria-label="Published by vscjava. 38.0M installs."><div class="icon-cell"><img class="icon" src="https://vscjava.gallerycdn.vsassets.io/extensions/vscjava/vscode-java-pack/0.29.2025081500/1755483596246/Microsoft.VisualStudio.Services.Icons.Default" alt="Extension Pack for Java"></div><div class="core-info-cell"><div class="name" title="Extension Pack for Java"><span>Extension Pack for Java</span></div><div class="core-info-second-row"><span class="installs"><span class="install-icon"></span><span class="install-count">38.0M</span></span><div class="publisher"><span>vscjava</span></div></div></div></div></div></a></div><div class="clearfix"></div></div></div></div>
				<p class="text-right">
					<a href="https://marketplace.visualstudio.com/vscode" target="_blank">See more in the Marketplace</a>
				</p>
			</div>

			<div>
				<h2 id="privacy">Privacy</h2>
				<p>By default, VS Code auto-updates to new versions, and collects usage data and crash report
					information. You
					may opt out of these defaults by disabling them as instructed below:</p>
				<div>
					<p><a href="/docs/supporting/faq#_how-do-i-opt-out-of-vs-code-autoupdates">How do I disable auto
							update?</a></p>
					<p><a href="/docs/supporting/faq#_how-to-disable-crash-reporting">How do I disable crash
							reporting?</a></p>
					<p><a href="/docs/supporting/faq#_how-to-disable-telemetry-reporting">How do I disable usage
							reporting?</a></p>
				</div>
			</div>
			<div class="feedback"><div class="widget"><form aria-label="Feedback"><div class="buttons"><h3 class="feedback-header">Was this documentation helpful?</h3><br><button value="1">Yes<span class="sr-only"> , this page was helpful</span></button><button value="0">No<span class="sr-only"> , this page was not helpful</span></button></div></form></div></div>
		</div>
		<!-- end of page connect widget -->
		<div class="col-xs-12 visible-xs">
			<div class="connect-widget"><ul class="connect-links"><li><a href="/feed.xml" target="_blank"><img alt="RSS" src="/assets/community/sidebar/rss.svg">RSS Feed</a></li><li><a href="https://stackoverflow.com/questions/tagged/vscode" target="_blank" rel="noopener noreferrer"><img alt="Stackoverflow" src="/assets/community/sidebar/stackoverflow.svg">Ask questions</a></li><li><a href="https://go.microsoft.com/fwlink/?LinkID=533687" target="_blank" rel="noopener noreferrer"><img alt="Twitter" src="/assets/community/sidebar/twitter.svg">Follow @code</a></li><li id="connect-uservoice"><a href="https://go.microsoft.com/fwlink/?LinkID=533482" target="_blank" rel="noopener noreferrer"><img alt="GitHub" src="/assets/community/sidebar/github.svg">Request features</a></li><li id="connect-github"><a href="https://www.github.com/Microsoft/vscode/issues" target="_blank" rel="noopener noreferrer"><img alt="Issues" src="/assets/community/sidebar/issue.svg">Report issues</a></li><li id="connect-youtube"><a href="https://www.youtube.com/channel/UCs5Y5_7XK8HLDX0SLNwkd3w" target="_blank" rel="noopener noreferrer"><img alt="YouTube" src="/assets/community/sidebar/youtube.svg">Watch videos</a></li></ul></div>
		</div>
	</div>
</div>
		</div>
	</div>

	<footer role="contentinfo" class="container">
		<div class="footer-container">
			<div class="footer-row">
				<div class="footer-social">
					<ul class="links">
						<li>
							<a href="https://github.com/microsoft/vscode"><img src="/assets/icons/github-icon.svg" alt="VS Code on Github"></a>
						</li>
						<li>
							<a href="https://go.microsoft.com/fwlink/?LinkID=533687"><img src="/assets/icons/x-icon.svg" class="x-icon" alt="Follow us on X"></a>
						</li>
						<li>
							<a href="https://www.linkedin.com/showcase/vs-code"><img src="/assets/icons/linkedin-icon.svg" alt="VS Code on LinkedIn"></a>
						</li>
						<li>
							<a href="https://bsky.app/profile/vscode.dev"><img src="/assets/icons/bluesky-icon.svg" alt="VS Code on Bluesky"></a>
						</li>
						<li>
							<a href="https://www.reddit.com/r/vscode/"><img src="/assets/icons/reddit-icon.svg" alt="Join the VS Code community on Reddit"></a>
						</li>
						<li>
							<a href="https://www.vscodepodcast.com"><img src="/assets/icons/podcast-icon.svg" alt="The VS Code Insiders Podcast"></a>
						</li>
						<li>
							<a href="https://www.tiktok.com/@vscode"><img src="/assets/icons/tiktok-icon.svg" alt="VS Code on TikTok"></a>
						</li>
						<li>
							<a href="https://www.youtube.com/@code"><img src="/assets/icons/youtube-icon.svg" alt="VS Code on YouTube"></a>
						</li>
						<script>
							function manageConsent() {
								if (siteConsent && siteConsent.isConsentRequired) {
									siteConsent.manageConsent();
								}
							}
						</script>
					</ul>
					<a id="footer-microsoft-link" class="microsoft-logo" href="https://www.microsoft.com">
						<img src="/assets/icons/microsoft.svg" alt="Microsoft homepage">
					</a>
				</div>
			</div>
			<div class="footer-row">
				<ul class="links">
					<li><a id="footer-support-link" href="https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=d66407ed-3967-b000-4cfb-2c318cad363d" target="_blank" rel="noopener">Support</a></li>
					<li><a id="footer-privacy-link" href="https://go.microsoft.com/fwlink/?LinkId=521839" target="_blank" rel="noopener">Privacy</a></li>
					<li style="display: none;"><a id="footer-cookie-link" style="cursor: pointer;" onclick="manageConsent()" target="_blank" rel="noopener">Manage Cookies</a></li>
					<li><a id="footer-terms-link" href="https://www.microsoft.com/legal/terms-of-use" target="_blank" rel="noopener">Terms of Use</a></li>
					<li><a id="footer-license-link" href="/License" target="_blank" rel="noopener">License</a></li>
				</ul>
			</div>
		</div>
	</footer>
	<script type="module">
		document.addEventListener('DOMContentLoaded', () => {
			const copilotDeepLinks = document.querySelectorAll('.copilot-deep-link');
			if (copilotDeepLinks.length === 0) {
				return;
			}
			if (window.innerWidth < 992) {
				for (const link of copilotDeepLinks) {
					link.href = 'https://aka.ms/vscode-activatecopilotfree';
				}
			}
		});
	</script>

	<script src="/dist/index.js"></script>

	

	<script type="application/ld+json">
		{
			"@context" : "http://schema.org",
			"@type" : "SoftwareApplication",
			"name" : "Visual Studio Code",
			"softwareVersion": "1.103",
			"offers": {
				"@type": "Offer",
				"price": "0",
				"priceCurrency": "USD"
			},
			"applicationCategory": "DeveloperApplication",
			"applicationSubCategory": "Text Editor",
			"alternateName": "VS Code",
			"datePublished": "2021-11-03",
			"operatingSystem": "Mac, Linux, Windows",
			"logo": "https://code.visualstudio.com/assets/apple-touch-icon.png",
			"screenshot": "https://code.visualstudio.com/assets/home/home-screenshot-win.png",
			"releaseNotes": "https://code.visualstudio.com/updates",
			"downloadUrl": "https://code.visualstudio.com/download",
			"license": "https://code.visualstudio.com/license",
			"softwareRequirements": "https://code.visualstudio.com/docs/supporting/requirements",
			"url" : "https://code.visualstudio.com",
			"author": {
				"@type": "Organization",
				"name": "Microsoft"
			},
			"publisher": {
				"@type": "Organization",
				"name": "Microsoft"
			},
			"maintainer": {
				"@type": "Organization",
				"name": "Microsoft"
			},
			"potentialAction": {
				"@type": "SearchAction",
				"target": "https://code.visualstudio.com/Search?q={search_term_string}",
				"query-input": "required name=search_term_string"
			},
			"sameAs" : [
				"https://en.wikipedia.org/wiki/Visual_Studio_Code",
				"https://twitter.com/code",
				"https://www.youtube.com/code",
				"https://www.tiktok.com/@vscode",
				"https://github.com/microsoft/vscode"
			]
		}
	</script>

  
</body></html>
<ul
  <label 
