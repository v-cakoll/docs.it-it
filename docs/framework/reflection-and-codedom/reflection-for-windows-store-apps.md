---
title: Reflection in .NET Framework per applicazioni Windows Store
description: Usare la reflection in .NET per le app di Windows Store. È disponibile un set di tipi di reflection e membri da usare nelle app di Windows Store, disponibili per la versione completa di .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- reflection, Windows Store apps
- .NET for Windows Store apps, TypeInfo class
ms.assetid: 0d07090c-9b47-4ecc-81d1-29d539603c9b
ms.openlocfilehash: 86bb633e97f0f88dc2a2a042b6897695a258cc3c
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865268"
---
# <a name="reflection-in-the-net-framework-for-windows-store-apps"></a>Reflection in .NET Framework per applicazioni Windows Store

A partire da .NET Framework 4,5, il .NET Framework include un set di tipi di reflection e membri da usare nelle app di Windows 8. x Store. Questi tipi e membri sono disponibili nella versione completa di .NET Framework, nonché in .NET per applicazioni Windows Store. In questo documento vengono illustrate le differenze principali tra questi e le relative controparti in .NET Framework 4 e versioni precedenti.  
  
 Se si sta creando un'app di Windows 8. x Store, è necessario usare i tipi e i membri di reflection in .NET per le app di Windows 8. x Store. Questi tipi e membri sono anche disponibili, ma non obbligatori, per l'utilizzo nelle applicazioni desktop, pertanto è possibile utilizzare lo stesso codice per entrambi i tipi di applicazioni.  
  
## <a name="typeinfo-and-assembly-loading"></a>Caricamento di assembly e TypeInfo  
 In .NET per le app di Windows 8. x Store la <xref:System.Reflection.TypeInfo> classe contiene alcune funzionalità della classe .NET Framework 4 <xref:System.Type> . Un oggetto <xref:System.Type> rappresenta un riferimento a una definizione di tipo, mentre un oggetto <xref:System.Reflection.TypeInfo> rappresenta la definizione del tipo stesso. Ciò consente di modificare gli oggetti <xref:System.Type> senza richiedere necessariamente al runtime di caricare l'assembly a cui fanno riferimento. L'acquisizione dell'oggetto <xref:System.Reflection.TypeInfo> associato comporta il caricamento dell'assembly.  
  
 <xref:System.Reflection.TypeInfo>contiene molti dei membri disponibili in <xref:System.Type> e molte delle proprietà di reflection in .NET per le app di Windows 8. x Store restituiscono raccolte di <xref:System.Reflection.TypeInfo> oggetti. Per ottenere un oggetto <xref:System.Reflection.TypeInfo> da un oggetto <xref:System.Type>, utilizzare il metodo <xref:System.Reflection.IReflectableType.GetTypeInfo%2A>.  
  
## <a name="query-methods"></a>Metodi di query  
 In .NET per le app di Windows 8. x Store è possibile usare le proprietà di reflection che restituiscono <xref:System.Collections.Generic.IEnumerable%601> raccolte anziché i metodi che restituiscono matrici. Nei contesti di reflection è possibile implementare l'attraversamento lazy di queste raccolte in caso di assembly o tipi di grandi dimensioni.  
  
 Tramite le proprietà di reflection vengono restituiti solo i metodi dichiarati in un oggetto particolare invece di attraversare l'albero di ereditarietà. Inoltre, non vengono utilizzati i parametri <xref:System.Reflection.BindingFlags> per l'applicazione di filtri. Al contrario, i filtri vengono applicati al codice utente, utilizzando le query LINQ nelle raccolte restituite. Per gli oggetti di reflection generati con il runtime (ad esempio come risultato di `typeof(Object)`), l'attraversamento dell'albero di ereditarietà viene eseguito in modo migliore se si utilizzano i metodi helper della classe <xref:System.Reflection.RuntimeReflectionExtensions>. Nei consumer di oggetti derivanti da contesti di reflection personalizzati non possono essere utilizzati questi metodi e l'attraversamento dell'albero di ereditarietà deve essere eseguito in modo autonomo.  
  
## <a name="restrictions"></a>Restrizioni  
 In un'app di Windows 8. x Store, l'accesso ad alcuni tipi di .NET Framework e membri è limitato. Non è ad esempio possibile chiamare .NET Framework metodi che non sono inclusi in .NET per le app di Windows 8. x Store, usando un <xref:System.Reflection.MethodInfo> oggetto. Inoltre, alcuni tipi e membri che non sono considerati sicuri nel contesto di un'app di Windows 8. x Store vengono bloccati, così come sono <xref:System.Runtime.InteropServices.Marshal> <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal> i membri e. Questa restrizione influisce solo sui tipi e sui membri di .NET Framework; il proprio codice o quello di terze parti può essere chiamato normalmente.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa i tipi e i membri di reflection in .NET per le app di Windows 8. x Store per recuperare i metodi e le proprietà del <xref:System.Globalization.Calendar> tipo, inclusi i metodi e le proprietà ereditati. Per eseguire questo codice, incollarlo nel file di codice per una pagina di Windows 8. x Store contenente un <xref:Windows.UI.Xaml.Controls.TextBlock?displayProperty=nameWithType> controllo denominato `textblock1` in un progetto denominato Reflection. Se si incolla il codice nel progetto con un nome diverso, assicurarsi di modificare il nome dello spazio dei nomi affinché corrisponda al progetto.  
  
 [!code-csharp[System.ReflectionWinStoreApp#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflectionwinstoreapp/cs/mainpage.xaml.cs#1)]
 [!code-vb[System.ReflectionWinStoreApp#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflectionwinstoreapp/vb/mainpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Vedi anche

- [Reflection](reflection.md)
