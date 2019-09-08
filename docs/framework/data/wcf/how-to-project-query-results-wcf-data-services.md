---
title: 'Procedura: Risultati query progetto (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- projection [WCF Data Services]
- WCF Data Services, projection
- query projection [WCF Data Services]
- WCF Data Services, querying
ms.assetid: 474ac625-8770-43ba-8320-d3315ea9530f
ms.openlocfilehash: 758bb01764fcfe195d4f940705316e7579be95ff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780016"
---
# <a name="how-to-project-query-results-wcf-data-services"></a>Procedura: Risultati query progetto (WCF Data Services)
La proiezione fornisce un meccanismo per ridurre la quantità di dati restituiti da una query specificando che solo determinate proprietà di un'entità vengano restituite nella risposta. È possibile eseguire proiezioni sui risultati di una [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] query utilizzando l' `$select` opzione query o utilizzando la clausola [Select](../../../csharp/language-reference/keywords/select-clause.md) ([Select](../../../visual-basic/language-reference/queries/select-clause.md) in Visual Basic) in una query LINQ. Per ulteriori informazioni, vedere [esecuzione di query sul servizio dati](querying-the-data-service-wcf-data-services.md).  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono creati al completamento della [WCF Data Services avvio rapido](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene illustrata una query LINQ che proietta le entità Customers in un nuovo tipo CustomerAddress contenente solo le proprietà specifiche dell'indirizzo e la proprietà Identity. Questa classe `CustomerAddress` viene definita nel client e attribuita in modo da essere riconosciuta come tipo di entità dalla libreria client.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddress)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene illustrata una query LINQ che proietta le entità Customers restituite in un nuovo tipo CustomerAddressNonEntity contenente solo le proprietà specifiche dell'indirizzo e nessuna proprietà Identity. Questa classe `CustomerAddressNonEntity` è definita nel client e non viene attribuita come tipo di entità.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono illustrate le definizioni `CustomerAddress` dei `CustomerAddressNonEntity` tipi e utilizzati negli esempi precedenti.  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customeraddress.vb#customeraddressdefinition)]
