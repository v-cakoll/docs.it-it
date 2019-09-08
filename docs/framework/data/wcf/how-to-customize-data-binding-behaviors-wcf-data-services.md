---
title: 'Procedura: Personalizzare i comportamenti di associazione dati (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, data binding
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
ms.openlocfilehash: c878096cba7d31e0b48727213ee1bb8239b8f690
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790756"
---
# <a name="how-to-customize-data-binding-behaviors-wcf-data-services"></a>Procedura: Personalizzare i comportamenti di associazione dati (WCF Data Services)
Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] è possibile fornire logica personalizzata chiamata da <xref:System.Data.Services.Client.DataServiceCollection%601> quando un oggetto viene aggiunto o rimosso dalla raccolta di associazioni o quando viene rilevata una modifica a una proprietà. Questa logica personalizzata viene fornita come metodi, a cui viene <xref:System.Func%602> fatto riferimento come delegati, `false` che restituiscono il valore quando il comportamento predefinito deve essere ancora eseguito quando il `true` metodo personalizzato viene completato e quando l'elaborazione successiva del l'evento deve essere arrestato.  
  
 Negli esempi riportati in questo argomento vengono forniti metodi personalizzati per entrambi i parametri `entityChanged` e `entityCollectionChanged` di <xref:System.Data.Services.Client.DataServiceCollection%601>. Negli esempi riportati in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono creati al completamento della [WCF Data Services avvio rapido](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 La pagina code-behind seguente per il file XAML determina la creazione di un oggetto <xref:System.Data.Services.Client.DataServiceCollection%601> con metodi personalizzati che vengono chiamati in caso di modifica dei dati associati alla raccolta di associazioni. Quando si verifica l'evento <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged>, il metodo fornito impedisce che un elemento rimosso dalla raccolta di associazioni venga eliminato dal servizio dati. Quando si verifica l'evento <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged>, il valore `ShipDate` viene convalidato per garantire che le modifiche non vengano apportate agli ordini già consegnati.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## <a name="example"></a>Esempio  
 Nel codice XAML seguente viene definita la finestra per l'esempio precedente.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](wcf-data-services-client-library.md)
