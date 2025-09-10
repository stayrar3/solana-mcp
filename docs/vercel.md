# Prompt Description for Vercel to Run the Solana MCP Server

## Overview

The Solana MCP (Model Context Protocol) Server is a powerful, serverless application that provides a range of tools and resources for developers working with the Solana blockchain. This server is designed to be highly scalable, cost-efficient, and easily accessible to users and AI agents worldwide.

## Key Components

1. __Serverless Function__: The core of the MCP server is a serverless function, defined in the `api/server.ts` file. This function is responsible for handling all incoming web requests and orchestrating the various components of the MCP server.

2. __Vercel Configuration (`vercel.json`)__: The `vercel.json` file at the root of the project provides the necessary configuration for Vercel to deploy and run the MCP server. This includes:

   - __Routing Rules (`rewrites`)__: Directs all incoming requests to the `/api/server` endpoint.
   - __Function Specifications (`functions`)__: Specifies the entry point (`api/server.ts`) and sets the maximum duration (800 seconds) for the serverless function to run.

3. __Environment Variables__: The MCP server relies on several environment variables, such as API keys for AI model providers and connection details for external resources. Vercel should be configured to securely inject these variables during deployment.

## Deployment Steps

1. __Clone the Repository__: Vercel should clone the `solana-mcp-official` repository from the provided Git URL.

2. __Install Dependencies__: Vercel should install the project dependencies by running `npm install` in the root directory.

3. __Configure Environment Variables__: Vercel should set the required environment variables, such as API keys and connection details, in the project's environment settings.

4. __Deploy the Serverless Function__: Vercel should deploy the `api/server.ts` file as a serverless function, using the configuration specified in the `vercel.json` file.

5. __Set Up Routing__: Vercel should configure the routing rules to direct all incoming requests to the `/api/server` endpoint, as specified in the `vercel.json` file.

6. __Verify Deployment__: Vercel should test the deployed MCP server by making requests to the `mcp.solana.com` domain and ensuring the server responds correctly.

## Performance Considerations

The MCP server is designed to handle complex AI tasks and potentially long-running operations. To accommodate this, the `vercel.json` file sets the `maxDuration` parameter to 800 seconds (13 minutes) for the serverless function. This generous timeout allows the server to complete its work without being prematurely cut off by Vercel.
