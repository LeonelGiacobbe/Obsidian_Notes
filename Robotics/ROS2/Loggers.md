A logger is a way to output messages (often error messages) to the console

### Logger Levels

- **DEBUG**: Provides detailed information, useful when diagnosing problems.
- **INFO**: Provides general operational information, like node initialization or events.
- **WARN**: Indicates a potential issue or something worth attention.
- **ERROR**: Reports a serious issue that is non-fatal but requires attention.
- **FATAL**: Reports a critical error, likely requiring the shutdown of a node or system.

### Usage
```c++
#include <rclcpp/rclcpp.hpp>
int main(int argc, char * argv[]) 
{
	// Create a ROS logger
	auto const logger { rclcpp::get_logger("nameOfRosNode") };

	// At different points in our code, we can then call 
	RCLCPP_ERROR(logger, "Planning failed!");
	RCLCPP_DEBUG(logger, "Function successfull");
	// Etcetera
}

```