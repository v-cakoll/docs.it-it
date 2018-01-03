---
title: 'Procedura: personalizzare i comportamenti del data binding (WCF Data Services)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, data binding
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e94ccb04028db3530705432309a808f17054d970
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-data-binding-behaviors-wcf-data-services"></a>Procedura: personalizzare i comportamenti del data binding (WCF Data Services)
Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] è possibile fornire logica personalizzata chiamata da <xref:System.Data.Services.Client.DataServiceCollection%601> quando un oggetto viene aggiunto o rimosso dalla raccolta di associazioni o quando viene rilevata una modifica a una proprietà. Questa logica personalizzata viene fornita come metodi, a cui fa riferimento come <xref:System.Func%602> delegati che restituiscono un valore di `false` quando il comportamento predefinito deve essere ancora eseguito al completamento del metodo personalizzato e `true` quando successive elaborazioni del evento deve essere arrestato.  
  
 Negli esempi riportati in questo argomento vengono forniti metodi personalizzati per entrambi i parametri `entityChanged` e `entityCollectionChanged` di <xref:System.Data.Services.Client.DataServiceCollection%601>. Negli esempi riportati in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 La pagina code-behind seguente per il file XAML determina la creazione di un oggetto <xref:System.Data.Services.Client.DataServiceCollection%601> con metodi personalizzati che vengono chiamati in caso di modifica dei dati associati alla raccolta di associazioni. Quando si verifica l'evento <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged>, il metodo fornito impedisce che un elemento rimosso dalla raccolta di associazioni venga eliminato dal servizio dati. Quando si verifica l'evento <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged>, il valore `ShipDate` viene convalidato per garantire che le modifiche non vengano apportate agli ordini già consegnati.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## <a name="example"></a>Esempio  
 Nel codice XAML seguente viene definita la finestra per l'esempio precedente.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## <a name="see-also"></a>Vedere anche  
 [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
