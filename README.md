# drip-faucet-log
 A poorly written piece of code you can use to log and calculate the DRIP Faucet performance of your wallet.

## DripWallet

To create a wallet, you must create an instance of the DripWallet object.

```
 w = new DripWallet({
    name: 'myWallet',
    deposits : 35,
    fee: 0.5,           
    dripValue: 50.51
});
```

### Options

Option | Type | Default | Description
------ | ---- | ------- | -----------
name|string|'demo'|Name of the wallet. Not used yet.
deposits|number|10|Quantity of DRIP deposited at start.
fee|number|0.50|Average fee in € for the BSC transactions. It can be overridden.
dripValue|number|50.00|DRIP Value in €. It can be overridden.
available|number|0|How much can be hydrated or claimed.
claimed|number|0|How much has been already claimed.
dayCount|number|0|Starting day.


### Methods

#### Claim (Once)

Use this method to log a CLAIM action with custom data such as transaction fee, updated DRIP value or the exact claimed amount.

```
w.claim({
    printLine:true,
    amount: 0.476, 
    fee: 0.59, 
    dripValue: 61.79,
    label:'Get The money'
});
```

#### Claim (Repeatedly)

Use this method to make a simulation.

```
w.repeatClaim({
    numDays:7,
    label:'Get the money'
});
```

#### Hydrate (Once)

Use this method to log a HYDRATE action with custom data such as transaction fee, updated DRIP value or the exact claimed amount.

```
w.hydrate({
    printLine:true,
    label:'Compounding!'
});
```

#### Hydrate (Repeatedly)

Use this method to make a simulation.

```
w.repeatHydrate({
    numDays:6
});
```

#### Grow Payout (Once)

Use this method when you didn't make any action that day.

```
w.growPayout({
    printLine:true,
    label:'Money piles up!'
});
```

#### Grow Payout (Repeatedly)

Use this method when you didn't make any action for some days.

```
w.repeatGrowPayout({
    numDays:6
});
```

#### Sell

Use this method when you claimed some amount of money and then you swapped it back into your BSC wallet.

```
w.sell({
    label:'Cash! €€€'
});
```

## Found a bug?
Write me at cryptosqwid@gmail.com

## Like this crappy code?
Buy me a beer. Send a tip to 0x7F82cecDeC38701729dEc9C62AE30897B55e0e50


