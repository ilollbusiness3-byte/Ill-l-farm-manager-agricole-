# iôll-farm-manager-agricole-
Application de gestion agricole Illôl farm manager agricole 


import 'package:flutter/material.dart';
import 'livestock_page.dart';

class DashboardPage extends StatelessWidget {
  const DashboardPage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Tableau de bord"),
        centerTitle: true,
      ),
      body: GridView.count(
        padding: const EdgeInsets.all(16),
        crossAxisCount: 2,
        crossAxisSpacing: 16,
        mainAxisSpacing: 16,
        children: [
          DashboardCard(
            icon: Icons.pets,
            title: "Élevage",
            onTap: () {
              Navigator.push(
                context,
                MaterialPageRoute(
                  builder: (_) => const LivestockPage(),
                ),
              );
            },
          ),

          const DashboardCard(
            icon: Icons.agriculture,
            title: "Agriculture",
          ),

          const DashboardCard(
            icon: Icons.water,
            title: "Pisciculture",
          ),

          const DashboardCard(
            icon: Icons.account_balance_wallet,
            title: "Comptabilité",
          ),

          const DashboardCard(
            icon: Icons.inventory,
            title: "Stock",
          ),

          const DashboardCard(
            icon: Icons.health_and_safety,
            title: "Santé",
          ),

          const DashboardCard(
            icon: Icons.analytics,
            title: "Rapports",
          ),

          const DashboardCard(
            icon: Icons.settings,
            title: "Paramètres",
          ),
        ],
      ),
    );
  }
}

class DashboardCard extends StatelessWidget {
  final IconData icon;
  final String title;
  final VoidCallback? onTap;

  const DashboardCard({
    super.key,
    required this.icon,
    required this.title,
    this.onTap,
  });

  @override
  Widget build(BuildContext context) {
    return Card(
      elevation: 5,
      shape: RoundedRectangleBorder(
        borderRadius: BorderRadius.circular(16),
      ),
      child: InkWell(
        onTap: onTap,
        borderRadius: BorderRadius.circular(16),
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Icon(
              icon,
              size: 55,
              color: Colors.green,
            ),
            const SizedBox(height: 10),
            Text(
              title,
              style: const TextStyle(
                fontSize: 18,
                fontWeight: FontWeight.bold,
              ),
            ),
          ],
        ),
      ),
    );
  }
}
