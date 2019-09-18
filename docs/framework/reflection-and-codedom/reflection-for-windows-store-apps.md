---
title: Reflection in .NET Framework per applicazioni Windows Store
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- reflection, Windows Store apps
- .NET for Windows Store apps, TypeInfo class
ms.assetid: 0d07090c-9b47-4ecc-81d1-29d539603c9b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9edab859900bf2001956045a5285801bb61d310
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045945"
---
# <a name="reflection-in-the-net-framework-for-windows-store-apps"></a>Reflection in .NET Framework per applicazioni Windows Store
A partire da .NET Framework 4.5, .NET Framework è incluso un set di tipi e membri di reflection che possono essere usati nelle app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Questi tipi e membri sono disponibili nella versione completa di .NET Framework, nonché in [.NET per app di Windows Store](https://go.microsoft.com/fwlink/?LinkID=225700). In questo documento vengono illustrate le differenze principali tra questi e le relative controparti in .NET Framework 4 e versioni precedenti.  
  
 Se si crea un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], è necessario utilizzare i tipi e i membri di reflection in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]. Questi tipi e membri sono anche disponibili, ma non obbligatori, per l'utilizzo nelle applicazioni desktop, pertanto è possibile utilizzare lo stesso codice per entrambi i tipi di applicazioni.  
  
## <a name="typeinfo-and-assembly-loading"></a>Caricamento di assembly e TypeInfo  
 Nella classe [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] di <xref:System.Reflection.TypeInfo> sono contenute alcune delle funzionalità della classe <xref:System.Type> di .NET Framework 4. Un oggetto <xref:System.Type> rappresenta un riferimento a una definizione di tipo, mentre un oggetto <xref:System.Reflection.TypeInfo> rappresenta la definizione del tipo stesso. Ciò consente di modificare gli oggetti <xref:System.Type> senza richiedere necessariamente al runtime di caricare l'assembly a cui fanno riferimento. L'acquisizione dell'oggetto <xref:System.Reflection.TypeInfo> associato comporta il caricamento dell'assembly.  
  
 Nell'oggetto <xref:System.Reflection.TypeInfo> sono contenuti molti dei membri disponibili nell'oggetto <xref:System.Type> e tramite molte delle proprietà di reflection in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] vengono restituite raccolte di oggetti <xref:System.Reflection.TypeInfo>. Per ottenere un oggetto <xref:System.Reflection.TypeInfo> da un oggetto <xref:System.Type>, utilizzare il metodo <xref:System.Reflection.IReflectableType.GetTypeInfo%2A>.  
  
## <a name="query-methods"></a>Metodi di query  
 In [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] utilizzare le proprietà di reflection tramite cui vengono restituite raccolte di oggetti <xref:System.Collections.Generic.IEnumerable%601> anziché i metodi mediante cui vengono restituite matrici. Nei contesti di reflection è possibile implementare l'attraversamento lazy di queste raccolte in caso di assembly o tipi di grandi dimensioni.  
  
 Tramite le proprietà di reflection vengono restituiti solo i metodi dichiarati in un oggetto particolare invece di attraversare l'albero di ereditarietà. Inoltre, non vengono utilizzati i parametri <xref:System.Reflection.BindingFlags> per l'applicazione di filtri. Al contrario, i filtri vengono applicati al codice utente, utilizzando le query LINQ nelle raccolte restituite. Per gli oggetti di reflection generati con il runtime (ad esempio come risultato di `typeof(Object)`), l'attraversamento dell'albero di ereditarietà viene eseguito in modo migliore se si utilizzano i metodi helper della classe <xref:System.Reflection.RuntimeReflectionExtensions>. Nei consumer di oggetti derivanti da contesti di reflection personalizzati non possono essere utilizzati questi metodi e l'attraversamento dell'albero di ereditarietà deve essere eseguito in modo autonomo.  
  
## <a name="restrictions"></a>Restrizioni  
 In un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] l'accesso ad alcuni tipi e membri di .NET Framework è limitato. Ad esempio, non è possibile chiamare i metodi di .NET Framework che non sono inclusi in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] tramite un oggetto <xref:System.Reflection.MethodInfo>. Inoltre, alcuni tipi e membri che non sono considerati sicuri nel contesto di un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] vengono bloccati, come i membri <xref:System.Runtime.InteropServices.Marshal> e <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal>. Questa restrizione influisce solo sui tipi e sui membri di .NET Framework; il proprio codice o quello di terze parti può essere chiamato normalmente.  
  
## <a name="example"></a>Esempio  
 In questo esempio vengono utilizzati i tipi e i membri di reflection in [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] per recuperare i metodi e le proprietà del tipo <xref:System.Globalization.Calendar>, inclusi i metodi e le proprietà ereditati. Per eseguire questo codice, incollarlo nel file di codice di una pagina di [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] contenente un controllo <xref:Windows.UI.Xaml.Controls.TextBlock?displayProperty=nameWithType> denominato `textblock1` in un progetto denominato Reflection. Se si incolla il codice nel progetto con un nome diverso, assicurarsi di modificare il nome dello spazio dei nomi affinché corrisponda al progetto.  
  
 [!code-csharp[System.ReflectionWinStoreApp#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflectionwinstoreapp/cs/mainpage.xaml.cs#1)]
 [!code-vb[System.ReflectionWinStoreApp#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflectionwinstoreapp/vb/mainpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Reflection](reflection.md)
- [.NET per app di Windows Store – API supportate](https://go.microsoft.com/fwlink/?LinkID=225700)
