# Misc PW Modules

## MiscShippingFees

Eg. in *templates/padloper/cart-edit.php*:

```
    <div class='misc-shipping-fees'>
<?php
  $shipping = $this->modules->get('MiscShippingFees');
  $shipping_fees = $shipping->getTotalShippingFees($items);

  echo '<table><th colspan="2">+ ' . __('Shipping') . ' (' . __("incl. VAT") . ')</th>';

  foreach($shipping_fees as $country => $price) {
    if($country == '*') {
      $country = __("Elsewhere");
    }

    $price = $cart->renderPriceAndCurrency($price);

    echo "<tr><td>{$country}</td><td>{$price}</td></tr>";
  }

  echo '</table>';
?>
    </div>
```

