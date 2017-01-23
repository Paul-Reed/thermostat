# thermostat
## A node-red interactive thermostat

![thermostat](/images/thermo.png)
### Setup a node-red static directory

Create a new static directory within your `.node-red` directory from which you can serve the CSS and Javascript files, for example 'public'.  
Git clone this repo into your newly created static directory;

    cd && cd .node-red/public
    git clone https://github.com/Paul-Reed/thermostat.git

Edit your node-red settings file, usually `nano /home/pi/.node-red/settings.js` as follows;

Firstly, edit httpStatic to read your static folder  
`httpStatic: '/home/pi/.node-red/public',`
and also if you havent already done so, httpAdminRoot must also be used to make the editor UI available at a path other than /. So for example if you changed the setting to `httpAdminRoot: '/admin',` then instead of your editor being accessed at the URL `192.168.168.13:1880/` you would use `192.168.168.13:1880/admin`

Then stop and restart node-red

### Use of thermostat

It is necessary to link both the CSS and Javascript script within the dashboard flow to your static folder, this is normally done by adding;

    <script type="text/javascript" src="/thermostat/thermojs/thermo.js"></script>
    <link rel="stylesheet" href="/thermostat/thermocss/thermo.min.css">
    
to a template node.

To load the thermometer widget;

    <div id="thermostat"></div>

There is an [example node-red flow](/example/example_flow) to get you started, once you have completed the above.

### Credit

Originally written by [Dal Handal](http://codepen.io/dalhundal), and enhanced by [Automatikas](http://www.ajso.lt/node-red/nest-thermostat-dashboard-html5-widget-node-red/)
