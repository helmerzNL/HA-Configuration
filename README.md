# HA-Configuration
My public HA creations


# My public HA Creations

## Table of contents

- [My public HA Creations](#my-public-ha-creations)
  - [Table of contents](#table-of-contents)
  - [Background](#background)
  - [Charging Pole](#charging-pole)


___

## Background

I noticed a screenshot from a colleague showing his HA dashboard in which wrote a nice hack to give him some insights of the status of the nearby public charging poles. So I asked him to share some code with me, which he did. 

This is the result my adoption of his code to my HA instance. You can find the code [here](https://github.com/helmerzNL/HA-Configuration/tree/main/Packages/house/car). Feel free to re-use it.


## Charging Pole
When you download the code, please notice that you need to change the [resource](./Packages/house/car/laadpaal_rest.yaml) parameter. Visit [Nextcharge.app](https://nextcharge.app/) and look for the charging pole you would like to add.

![Look up Charging Pole](./images/laadpaal_howto_01.png)

Now, press (F12, to open the Developer Tools) and click the url to open it in a new tab. 

![Click URL](./images/laadpaal_howto_02.png)

Copy this url and paste it in the *resource* field in the [laadpaal_rest.yaml](./Packages/house/car/laadpaal_rest.yaml) file.

Now restart Home Assistant and create a card showing the created sensors.

![Laadpaal](./images/laadpaal01.png)