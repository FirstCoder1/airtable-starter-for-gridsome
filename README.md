# Airtable starter for Gridsome

This starter is meant to act as a starting point/example for connecting [Gridsome](https://gridsome.org/) with [Airtable](https://airtable.com/).

## Install Gridsome CLI tool (if you dont' have it already)

`npm install --global @gridsome/cli`

## Create a Gridsome project

1. `gridsome create my-gridsome-site https://github.com/12vanblart/gridsome-airtable-starter.git` to install this starter
2. `cd my-gridsome-site` to open the folder
3. `gridsome develop` to start a local dev server at `http://localhost:8080`
4. Happy coding 🎉💻

## Configure your Airtable connection

Inside your `gridsome.config.js` file, you'll see the following:

```javascript
// gridsome.config.js //

module.exports = {
  siteName: 'Site Name',
  plugins: [
    {
      use: '@gridsome/source-airtable',
      options: {
        // Add these to a .env file
        // Details on finding these values can be found at:
        // https://gridsome.org/plugins/@gridsome/source-airtable
        apiKey: process.env.AIRTABLE_KEY, //required
        baseId: process.env.AIRTABLE_BASE, //required
        tableName: 'Events', //required
        typeName: 'Event', //required - needs to match template name
        route: '/events/:name' //optional
      }
    }
  ]
}

```

### dotenv file

[Details on Gridsome Environment Variables.](https://gridsome.org/docs/environment-variables)

You'll need to create the file `.env` in your root project directory (The same level as `gridsome.config.js`) with the following (replace with your values):

```
AIRTABLE_KEY=<apiKey>
AIRTABLE_BASE=<baseId>
```

You can learn more about getting these values from the [plugin page](https://gridsome.org/plugins/@gridsome/source-airtable).
