# Description

This is simple Chart.js Line React component.

# Quickstart

In project directory run command:

    bash install.bash

then open <code>index.html</code> file in your browser.

# Sample usage - basic

You can create <code>chart</code> object with data and send it to the <code>ChartLine</code> React component as <code>data</code>.

    import React from 'react';
    import ReactDOM from 'react-dom';
    import ChartLine from './react-chart-line.js';

    var chart = { msg: "", osX: [], osY: [] };

    for (var i=0,x=-10; i<20; i++,x++) {
      chart.osX[i] = x;
      chart.osY[i] = Math.sin(x)-Math.tan(x);
    }

    ReactDOM.render(
      <ChartLine data={chart}/>,
      document.getElementById('app')
    );

# Sample usage - update

If you send updated <code>chart</code> object again to the <code>ChartLine</code> React component as <code>data</code> it will update itself.

    function setRandomChart() {
      var chart = { msg: "", osX: [], osY: [] };
      for (var i=0,x=-10; i<20; i++,x++) {
        chart.osX[i] = x;
        chart.osY[i] = Math.random();
      }
      ReactDOM.render(
        <ChartLine data={chart}/>,
        document.getElementById('app')
      );
    }
    setInterval(() => { setRandomChart() }, 5000);

# License

MIT
