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
  String updateOrder(@PathVAriable @Valid @Min(value=1,message="{order.orderid.invalid}") Int
    String msg=infyPandaService.updateOrder(orderId, quantityNew);
    return msg;
  }

  @DeleteMapping("order/{orderId}")
  String cancelOrder(@PathVariable @Valid @Min(value=1,message="{order.orderid.invalid}") Int
    String msg=infyPnadService.cancelOrder(orderId);
    return msg;
  }

  <b> ExceptionControllerAdvice.java</b>
  @ExceptionHandler(Exception.class)
    public ResponseEntity<*ErrorInfy*> generalExceptionHandler(Exception ex)
    {
    logger.error(ex.getMessage(),ex);
    ErrorInfo errorInfo=new ErrorInfo();
    errorInfo.setErrorCode(HttpStatus.INTERNAL_SERVER_ERROR.value());
    error.Info.setErrorMsg(environment.getProperty("General.EXCEPTION_MESSAGE"));
    return new ResponseEntity<>(errorInfy,HttpStstus.INTERNAL_SERVER_ERROR);
    }

    @ExceptionHandler(InfyPandaException.class)
     public ResponseEntity<*ErrorInfo*> infyPandaExceptionHandler(InfyPandaException ex)
    {
     logger.error(ex.getMessage(),ex);
    ErrorInfo errorInfo=new ErrorInfo();
    errorInfo.setErrorCode(HttpStatus.BAREQUEST.value());
    error.Info.setErrorMsg(environment.getProperty(ex.getmessage()));
    return new ResponseEntity<*ErrorInfo*>(errorInfy,HttpStstus.BAD_REQUEST);
    }











  
</code></p>
