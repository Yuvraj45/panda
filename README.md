# panda
<p> <code> 
<b> DTO </b>
@Min(value=1,message="{order.quantity.invalid}")
private int quantity;

<b> infypanda controller</b>
import java.util.List;
@RsetController
@RequestMapping
@validated
public class InfyPandaController {
  @Autowired
  public InfyPandaService infyPandaService;

  @GetMapping("restaurants/{itemName}")
  List<*RestaurantDTO*> searchRestaurantWithItemName(@PathVariable @Valid String itemName) throws
    List<*RestaurantDTO*> lis=infyPandaService.searchRestaurantsWithItemName(item);
    return lis;
  }
  @GetMApping("ietm/{restaurantName}")
  List<*ItemDTO*> searchItemsByRestaurantName(@PathVariable @Valid @Pattern(regexp=^[\t]+[\t]+
    List<*ItemDTO*> List=infyPandaService.searchItemByRestaurantName(restaurantName);
    return List;

  @PostMapping("order")
  String placeOrder(@RequestBody OredrDTO orderDTO throws InfyPandaEXception {
    String msg=infyPandaService.placeOrder(orderDTO);
    return msg;
  }
    
  @PutMApping("order/{orderId}/{quantityNew}")")
  String updateOrder(@PathVAriable @Valid 











  
</code></p>
