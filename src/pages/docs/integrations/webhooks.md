---
title: "Custom Webhooks"
order: 121
page_id: "custom_webhooks"
warning: false
---

Postman provides a custom webhook integration which enables you to automate workflows between your favorite apps and services to get notifications, synchronize files, collect data, and more. It offers many services with predefined flows available for easy implementation.

You can configure a custom webhook with Postman to send events such as monitor results, team and collection-specific activity feeds, and to back up your Postman Collections.

## Configuring Custom Webhook URL

1. In the [Integrations](https://go.postman.co/workspaces) page, find Webhooks from a list of Postman’s 3rd party integrations.

[![custom_webhook](https://assets.postman.com/postman-docs/webhooks_view1.png)](https://assets.postman.com/postman-docs/webhooks_view1.png)  

Click **View Details** to go to the Webhooks main interface. You can also click **Configured Integrations** tab to set up other integrations, view available integrations for Custom Webhooks, or view all configured integrations.

[![webhooks_view2](https://assets.postman.com/postman-docs/webhooks_view2.png)](https://assets.postman.com/postman-docs/webhooks_view2.png)  

## Back up your Postman Collections

You can use custom webhooks to back up your Postman collections. This will require a few quick steps to set up:

1. Click **Add Integration**.
2. In the **Backup your Postman Collections** page:
   * Enter any name
   * Select the collection.
   * Enter the Webhook URL.
3. Click **Add Integration**.

[![webhooks collections1](https://assets.postman.com/postman-docs/webhooks_collections1.png)](https://assets.postman.com/postman-docs/webhooks_collections1.png)

Once the integration has been created, you can view it by navigating to **Configured Integrations**:

[![configured integrations](https://assets.postman.com/postman-docs/Configured_integrations.png)](https://assets.postman.com/postman-docs/Configured_integrations.png)

## **Backup Collections**

The following is a schema for Backup Collections:

```json
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "definitions": {},
  "id": "http://example.com/example.json",
  "properties": {
    "collection": {
      "id": "/properties/collection",
      "properties": {},
      "type": "object"
    }
  },
  "type": "object"
}
```

## Send collection activity feed to Custom Webhooks

The activity feed is where you can view all changes being made to your Postman collection by your teammates. Integrating with Webhooks gives you the freedom to connect with email services like Outlook, Gmail, or a custom SMTP service.

To send collection activity feed to Custom webhooks:

1. Click **Add Integration**.
2. In the **Collection Activity Feed** page, enter the webhook URL to send team updates to this specific URL.
3. Click **Add Integration**.

## Send Monitor run results to Custom Webhooks

Postman Monitors allows you to run your collections on a schedule without any manual intervention. With the Custom webhooks, you can use those results by connecting to other available services.

To send monitor run results to Custom Webhooks:

1. Click **Add Integration**.
2. In the **Monitor Run Results** page, select the monitor you want to send to Custom webhooks.
3. Click **Add Integration**.

[![webhook_mon_runs](https://assets.postman.com/postman-docs/webhooks_monitors1.png)](https://assets.postman.com/postman-docs/webhooks_monitors1.png)

You can also configure advanced options to alert you when a monitor run completes or when three failures occur and the first monitor run after those failures completes successfully.

Your integration has now been set up successfully. Whenever your monitor runs, the results will be posted to your webhook.

## Monitor Run Results

The following is a schema for monitor run results:

```json
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "definitions": {},
  "id": "http://example.com/example.json",
  "properties": {
    "collection_name": {
      "id": "/properties/collection_name",
      "type": "string"
    },
    "collection_uid": {
      "id": "/properties/collection_uid",
      "type": "string"
    },
    "environment_name": {
      "id": "/properties/environment_name",
      "type": "string"
    },
    "environment_uid": {
      "id": "/properties/environment_uid",
      "type": "string"
    },
    "metrics": {
      "id": "/properties/metrics",
      "properties": {
        "errors":
          "id": "/properties/metrics/properties/errors",
          "type": "integer"
        },
        "failedTests": {
          "id": "/properties/metrics/properties/failedTests",
          "type": "integer"
        },
        "passedTests": {
          "id": "/properties/metrics/properties/passedTests",
          "type": "integer"
        },
        "requestCount": {
          "id": "/properties/metrics/properties/requestCount",
          "type": "integer"
        },
        "totalLatency": {
          "id": "/properties/metrics/properties/totalLatency",
          "type": "integer"
        },
        "warnings": {
          "id": "/properties/metrics/properties/warnings",
          "type": "integer"
        }
      },
      "type": "object"
    },
    "monitor_name": {
      "id": "/properties/monitor_name",
      "type": "string"
    },
    "monitor_uid": {
      "id": "/properties/monitor_uid",
      "type": "string"
    },
    "user_id": {
      "id": "/properties/user_id",
      "type": "string"
    },
    "user_name": {
      "id": "/properties/user_name",
      "type": "string"
    }
  },
  "type": "object"
}
```

## Send a team activity feed to custom webhooks

The activity feed is where you can track changes made to your collections and within your team. Integrating with webhooks gives you the freedom to connect with many services.

To send a team activity feed to a custom webhook:

1. Click the **Add Integration** button.
2. In the **Team Activity Feed** page, enter the webhook URL to send team updates to this specific URL.
3. Click the **Add Integration** button.

[![custom webhook](https://assets.postman.com/postman-docs/WS-integrations-msFlow-teamactivityfeed.png)](https://assets.postman.com/postman-docs/WS-integrations-msFlow-teamactivityfeed.png)

## Team Activity

The following is a schema for Team Activity:

```json
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "definitions": {},
  "id": "http://example.com/example.json",
  "properties": {
    "action": {
      "id": "/properties/action",
      "type": "string"
    },
    "collection_name": {
      "id": "/properties/collection_name",
      "type": "string"
    },
    "collection_uid": {
      "id": "/properties/collection_uid",
      "type": "string"
    },
    "message": {
      "id": "/properties/message",
      "type": "string"
    },
    "model": {
      "id": "/properties/model",
      "type": "string"
    },
    "model_name": {
      "id": "/properties/model_name",
      "type": "string"
    },
    "model_uid": {
      "id": "/properties/model_uid",
      "type": "string"
    },
    "user_id": {
      "id": "/properties/user_id",
      "type": "string"
    },
    "user_name": {
      "id": "/properties/user_name",
      "type": "string"
    }
  },
  "type": "object"
}
```