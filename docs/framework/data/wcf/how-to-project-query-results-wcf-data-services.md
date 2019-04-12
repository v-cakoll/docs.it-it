---
title: 'Procedura: Risultati della Query di progetto (WCF Data Services)'
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
ms.openlocfilehash: 4b0646c2ad45a86691b86b1dd5f112f598ee2dfd
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/12/2019
ms.locfileid: "59518194"
---
# <a name="how-to-project-query-results-wcf-data-services"></a>Procedura: Risultati della Query di progetto (WCF Data Services)
La proiezione fornisce un meccanismo per ridurre la quantità di dati restituiti da una query specificando che solo determinate proprietà di un'entità vengano restituite nella risposta. È possibile eseguire proiezioni sui risultati di un' [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] tramite l'utilizzo di query il `$select` opzione di query o utilizzando il [selezionare](~/docs/csharp/language-reference/keywords/select-clause.md) clausola ([selezionare](~/docs/visual-basic/language-reference/queries/select-clause.md) in Visual Basic) in una query LINQ. Per altre informazioni, vedere [l'esecuzione di query al servizio dati](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene illustrata una query LINQ che proietta le entità Customers in un nuovo tipo CustomerAddress contenente solo le proprietà specifiche dell'indirizzo e la proprietà Identity. Questa classe `CustomerAddress` viene definita nel client e attribuita in modo da essere riconosciuta come tipo di entità dalla libreria client.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddress)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene illustrata una query LINQ che proietta le entità Customers restituite in un nuovo tipo CustomerAddressNonEntity contenente solo le proprietà specifiche dell'indirizzo e nessuna proprietà Identity. Questa classe `CustomerAddressNonEntity` è definita nel client e non viene attribuita come tipo di entità.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente mostra le definizioni del `CustomerAddress` e `CustomerAddressNonEntity` tipi utilizzati negli esempi precedenti.  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customeraddress.vb#customeraddressdefinition)]
