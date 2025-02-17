---
sidebarDepth: 4
---

# CREATING A TAGO CONNECTION

## Collecting Expected Information

**Parameters required**

| Field | Description |
| ------ | ----------- |
| ```Authorization``` | The key generated at **https://admin.tago.io/devices/authorization**.|

### Authorization

The Authorization is the **API key** generated in [TAGO](https://admin.tago.io/).
Follow these steps to generate a new **AUTHORIZATION** in your TAGO admin interface:

1. Open this [link](https://admin.tago.io/). Go to the **Devices** section, and **Authorization** in the top right corner.

![goto_authorization](./images/authorization.png)

2. You can now copy your **Authorization** key, by clicking the **Copy** button.

![generate_key](./images/copy_authorization.png)

## Creating a Connection With API

The creation of a connection establishes a unidirectional messaging transport link to the cloud provider.

To do this, you need to use the **Connections** group resource:
*	`POST/connections` to create a new Connection instance
*	`PUT/connections` to update a Connection instance
*	`DELETE/connections` to delete a Connection instance


::: tip Note
We follow the REST-full API pattern, when updating configuration properties for a connection resource. Thus, you must also provide the whole configuration again.
:::

Example for creation of a new connection instance :

```json
POST /connections
{
  "name":"Actility To Tago",
  "connectorId":"actility-http-iot",
  "configuration": {
      "destinationURL":"https://actility.middleware.tago.io/uplink?authorization=<tago_authorization>"
  },
  "brand":"TAGO"
}
```

The following table lists the properties applicable to a connection instance.

| Field | Description |
| ------ | ----------- |
| ```connectorId``` | Must be set to actility-http-iot for Tago platform. |
| ```configuration/destinationURL``` | Must be set to **https://actility.middleware.tago.io/uplink?authorization=tago_authorization**. |
| ```tago_authorization``` | Must be raplaced by your Authorization Token (refer to [this section](#authorization)). |
| ```brand``` | Must be set to ```TAGO```. |

::: warning Important note
All properties are not present in this example. You can check the rest of these properties in the [common parameters section](../../Getting_Started/Setting_Up_A_Connection_instance/About_connections.html#common-parameters).
:::

## Creating a Connection With UI

1. Click Applications -> Create -> View More Applications Type.

![more_applications](./images/coming_soon.png)

2. Then, a new page will open. Select the connection type: **Tago**.

![select_tago](./images/coming_soon.png)

3. Fill in the form as in the example below and click on **Create**.

![form_filled](./images/coming_soon.png)

::: tip Note
Parameters marked with * are mandatory.
:::

* A notification appears on the upper right side of your screen to confirm that the application has been created.

![notification_creation](./images/coming_soon.png)

4. After creating the application, you will be redirected to the application details.

![application_details](./images/coming_soon.png)

## Limitations

Limitations depends on Account Plan you own (refer to this [link](https://docs.tago.io/en/articles/114-account-plans)).

## Displaying information to know if it worked

1.	Connect to your [TAGO account](https://admin.tago.io/).

2.	Go to **Devices** section and click the **"+ Add Device"** buton to create a new **Device**.

![add_device](./images/add_device.png)

3.  Choose **LoRaWan Actility** in the scrolling menu, and look for the **Device** model you want to add.

![choose_device](./images/choose_device.png)

4.  Fill in the form, with the **Device name** and the **Device EUI** (find **Device EUI** at https://yourdomain.com/tpe/#/devices/list)

![fill_device_form](./images/fill_device_form.png)

5.  Wait a few minutes, to see if you get an **input** from your **Device** (see exemple bellow).

![device_input](./images/device_input.png)

## Troubleshooting

As for now, there are no detected bugs.