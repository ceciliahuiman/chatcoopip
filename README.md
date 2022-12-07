# chatcoopip
import 'package:chatcoopip/inner_screens/product_details.dart';
import 'package:chatcoopip/services/global_method.dart';
import 'package:chatcoopip/services/utils.dart';
import 'package:chatcoopip/widgets/text_widget.dart';
import 'package:flutter/material.dart';

class OrdersWidget extends StatefulWidget {
  const OrdersWidget({super.key});

  @override
  State<OrdersWidget> createState() => _OrdersWidgetState();
}

class _OrdersWidgetState extends State<OrdersWidget> {
  @override
  Widget build(BuildContext context) {
    Size size = Utils(context).getScreenSize;
    final Color color = Utils(context).color;
    return ListTile(
      onTap: () {
        GlobalMethods.navigateTo(
            context: context, routeName: ProductDetails.routeName);
      },
      subtitle: const Text('Pagado  \$300'),
      leading: Container(
          clipBehavior: Clip.antiAlias,
          decoration: BoxDecoration(
            borderRadius: BorderRadius.circular(12),
          ),
          child: Image.asset(
            'assets/rascadores/Madrid.jpg',
            fit: BoxFit.scaleDown,
            width: size.width * 0.2,
          )),
      title:
          TextWidget(text: 'Madrid', color: color, textsize: 22, isTitle: true),
      trailing: TextWidget(text: '22/10/2022', color: color, textsize: 20),
    );
  }
}
