---
title: 'Procedura: definire e utilizzare provider di formati numerici personalizzati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- custom numeric format strings
- numbers [.NET Framework], custom numeric format strings
- displaying date and time data
- format providers [.NET Framework]
- custom format strings
ms.assetid: a281bfbf-6596-45ed-a2d6-3782d535ada2
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e44a909eb92f0d9dfa21980a918a2d370dcf427
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-define-and-use-custom-numeric-format-providers"></a>Procedura: definire e utilizzare provider di formati numerici personalizzati
Il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] offre un ampio controllo sulla rappresentazione di stringa dei valori numerici. e supporta le funzionalità seguenti per la personalizzazione del formato di tali valori:  
  
-   Stringhe in formato numerico standard, che forniscono un insieme predefinito di formati per la conversione dei numeri nella rispettiva rappresentazione di stringa. È possibile utilizzarli con qualsiasi metodo di formattazione, ad esempio numerica <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>, che ha un `format` parametro. Per informazioni dettagliate, vedere [stringhe di formato numerico Standard](../../../docs/standard/base-types/standard-numeric-format-strings.md).  
  
-   Stringhe in formato numerico personalizzato che forniscono un insieme di simboli che possono essere combinati per definire identificatori di formato numerico personalizzato. Possono inoltre essere utilizzati con qualsiasi metodo di formattazione, ad esempio numerica <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>, che ha un `format` parametro. Per informazioni dettagliate, vedere [stringhe di formato numerico personalizzato](../../../docs/standard/base-types/custom-numeric-format-strings.md).  
  
-   Custom <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo> oggetti che definiscono i simboli e i modelli utilizzati per la visualizzazione di valori numerici le rappresentazioni di stringa di formato. È possibile utilizzarli con qualsiasi metodo di formattazione, ad esempio numerica <xref:System.Int32.ToString%2A>, che ha un `provider` parametro. In genere, il `provider` parametro viene utilizzato per specificare informazioni di formattazione specifiche delle impostazioni cultura.  
  
 In alcuni casi, ad esempio quando un'applicazione deve visualizzare un numero di account formattato, un numero di identificazione o un codice postale, queste tre tecniche non sono adatte. Il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] consente inoltre di definire un oggetto di formattazione che non è né un <xref:System.Globalization.CultureInfo> né <xref:System.Globalization.NumberFormatInfo> oggetto per determinare come viene formattato un valore numerico. In questo argomento sono contenute istruzioni dettagliate per l'implementazione di tale oggetto ed è anche riportato un esempio di formattazione di numeri di telefono.  
  
### <a name="to-define-a-custom-format-provider"></a>Per definire un provider di formato personalizzato  
  
1.  Definire una classe che implementa il <xref:System.IFormatProvider> e <xref:System.ICustomFormatter> interfacce.  
  
2.  Implementare il metodo <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>. <xref:System.IFormatProvider.GetFormat%2A>è un metodo di callback che il metodo di formattazione (ad esempio il <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> metodo) richiama per recuperare l'oggetto è responsabile della formattazione personalizzata. Un'implementazione tipica delle <xref:System.IFormatProvider.GetFormat%2A> esegue le operazioni seguenti:  
  
    1.  Determina se il <xref:System.Type> oggetto passato come un metodo parametro rappresenta un <xref:System.ICustomFormatter> interfaccia.  
  
    2.  Se il parametro rappresenta il <xref:System.ICustomFormatter> interfaccia <xref:System.IFormatProvider.GetFormat%2A> restituisce un oggetto che implementa il <xref:System.ICustomFormatter> interfaccia che è responsabile della formattazione personalizzata. In genere, l'oggetto di formattazione personalizzata restituisce se stesso.  
  
    3.  Se il parametro rappresenta il <xref:System.ICustomFormatter> interfaccia <xref:System.IFormatProvider.GetFormat%2A> restituisce `null`.  
  
3.  Implementare il metodo <xref:System.ICustomFormatter.Format%2A>. Questo metodo viene chiamato dal <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> metodo ed è responsabile di restituire la rappresentazione di stringa di un numero. L'implementazione del metodo in genere implica le attività seguenti:  
  
    1.  Facoltativamente, assicurarsi che il metodo sia correttamente destinato a fornire servizi di formattazione esaminando il `provider` parametro. Per la formattazione di oggetti che implementano entrambi <xref:System.IFormatProvider> e <xref:System.ICustomFormatter>, questa operazione richiede il test di `provider` parametro per verificarne l'uguaglianza con l'oggetto di formattazione corrente.  
  
    2.  Stabilire se l'oggetto di formattazione deve supportare identificatori di formato personalizzato. Ad esempio, un identificatore di formato "N" potrebbe indicare che un numero di telefono degli Stati Uniti deve essere restituito in formato NANP e un identificatore di formato "I" potrebbe indicare l'output in formato ITU-T Recommendation E.123. Se si usano identificatori di formato, il metodo deve gestire l'identificatore di formato specifico. Viene passato al metodo di `format` parametro. Se l'identificatore non è presente, il valore della `format` parametro <xref:System.String.Empty?displayProperty=nameWithType>.  
  
    3.  Recuperare il valore numerico passato al metodo come la `arg` parametro. Eseguire le eventuali modifiche necessarie per convertirlo nella relativa rappresentazione di stringa.  
  
    4.  Restituire la rappresentazione di stringa del `arg` parametro.  
  
### <a name="to-use-a-custom-numeric-formatting-object"></a>Per usare un oggetto di formattazione numerica personalizzata  
  
1.  Creare una nuova istanza della classe di formattazione personalizzata.  
  
2.  Chiamare il <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> metodo di formattazione, passando l'oggetto di formattazione personalizzata, l'identificatore di formattazione (o <xref:System.String.Empty?displayProperty=nameWithType>, se non viene utilizzata una) e il valore numerico da formattare.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definito un provider di formato numerico personalizzato denominato `TelephoneFormatter` che converte un numero che rappresenta un numero telefonico degli Stati Uniti nel suo formato NANP oppure E.123. Il metodo gestisce due identificatori di formato, "N" (che restituisce il formato NANP) e "I" (che restituisce il formato E.123 internazionale).  
  
 [!code-csharp[Formatting.HowTo.NumericValue#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#1)]
 [!code-vb[Formatting.HowTo.NumericValue#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#1)]  
  
 Il provider di formato numerico personalizzate sono utilizzabili solo con il <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> metodo. Gli altri overload di metodi di formattazione numerica (ad esempio `ToString`) che hanno un parametro di tipo <xref:System.IFormatProvider> passano il <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> implementazione un <xref:System.Type> oggetto che rappresenta il <xref:System.Globalization.NumberFormatInfo> tipo. In cambio, prevedono che il metodo per restituire un <xref:System.Globalization.NumberFormatInfo> oggetto. In caso contrario, il provider di formato numerico personalizzato viene ignorato e <xref:System.Globalization.NumberFormatInfo> dell'oggetto per le impostazioni cultura correnti viene utilizzata al suo posto. Nell'esempio di `TelephoneFormatter.GetFormat` metodo gestisce la possibilità che possa essere passato erroneamente a un metodo di formattazione esaminando il parametro del metodo e restituendo numerica `null` se rappresenta un tipo diverso da <xref:System.ICustomFormatter>.  
  
 Se un provider di formato numerico personalizzato supporta un set di identificatori di formato, assicurarsi di fornire un comportamento predefinito, se non viene fornito alcun identificatore di formato nell'elemento di formato utilizzato nel <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> chiamata al metodo. Nell'esempio "N" è l'identificatore di formato predefinito. È pertanto possibile convertire un numero in un numero di telefono formattato specificando un identificatore di formato esplicito. Nell'esempio riportato di seguito viene illustrata questa chiamata al metodo.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#2)]
 [!code-vb[Formatting.HowTo.NumericValue#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#2)]  
  
 L'esecuzione della conversione è possibile anche in assenza di identificatori di formato. Nell'esempio riportato di seguito viene illustrata questa chiamata al metodo.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#3)]
 [!code-vb[Formatting.HowTo.NumericValue#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#3)]  
  
 Se non è definito alcun identificatore di formato predefinito, l'implementazione del <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> metodo deve includere il codice seguente in modo che .NET di fornire la formattazione che il codice non è supportata.  
  
 [!code-csharp[System.ICustomFormatter.Format#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.ICustomFormatter.Format/cs/format.cs#1)]
 [!code-vb[System.ICustomFormatter.Format#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.ICustomFormatter.Format/vb/Format.vb#1)]  
  
 In questo esempio, il metodo che implementa <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> è destinato a essere un metodo di callback per la <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> metodo. Pertanto, viene esaminato il `formatProvider` parametro per determinare se contiene un riferimento all'oggetto corrente `TelephoneFormatter` oggetto. Il metodo può tuttavia essere chiamato anche direttamente dal codice. In tal caso, è possibile utilizzare il `formatProvider` parametro per fornire un <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo> oggetto che fornisce informazioni di formattazione specifiche delle impostazioni cultura.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Compilare il codice nella riga di comando con csc.exe o vb.exe. Per compilare il codice in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], inserirlo in un modello di progetto applicazione console.  
  
## <a name="see-also"></a>Vedere anche  
 [Esecuzione di operazioni di formattazione](../../../docs/standard/base-types/performing-formatting-operations.md)
