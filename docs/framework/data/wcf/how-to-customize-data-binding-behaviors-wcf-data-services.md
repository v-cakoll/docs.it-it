---
title: 'Procedura: Personalizzare i Data Binding dei comportamenti (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, data binding
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
ms.openlocfilehash: f55c9790b8300a1a3f26e031a17a0982638b562b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517421"
---
# <a name="how-to-customize-data-binding-behaviors-wcf-data-services"></a>Procedura: Personalizzare i Data Binding dei comportamenti (WCF Data Services)
Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] è possibile fornire logica personalizzata chiamata da <xref:System.Data.Services.Client.DataServiceCollection%601> quando un oggetto viene aggiunto o rimosso dalla raccolta di associazioni o quando viene rilevata una modifica a una proprietà. Questa logica personalizzata viene fornita come metodi, farvi riferimento come <xref:System.Func%602> delegati che restituiscono un valore di `false` quando il comportamento predefinito deve essere eseguito comunque al completamento del metodo personalizzato e `true` quando successiva elaborazione del evento deve essere arrestato.  
  
 Negli esempi riportati in questo argomento vengono forniti metodi personalizzati per entrambi i parametri `entityChanged` e `entityCollectionChanged` di <xref:System.Data.Services.Client.DataServiceCollection%601>. Negli esempi riportati in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 La pagina code-behind seguente per il file XAML determina la creazione di un oggetto <xref:System.Data.Services.Client.DataServiceCollection%601> con metodi personalizzati che vengono chiamati in caso di modifica dei dati associati alla raccolta di associazioni. Quando si verifica l'evento <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged>, il metodo fornito impedisce che un elemento rimosso dalla raccolta di associazioni venga eliminato dal servizio dati. Quando si verifica l'evento <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged>, il valore `ShipDate` viene convalidato per garantire che le modifiche non vengano apportate agli ordini già consegnati.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## <a name="example"></a>Esempio  
 Nel codice XAML seguente viene definita la finestra per l'esempio precedente.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
