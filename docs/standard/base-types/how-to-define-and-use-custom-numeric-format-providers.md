---
title: 'Procedura: Definire e usare provider di formati numerici personalizzati'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: d12899fff7d9e6cb63728ba0b160b70fa2a41a1a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290513"
---
# <a name="how-to-define-and-use-custom-numeric-format-providers"></a>Procedura: Definire e usare provider di formati numerici personalizzati
.NET Framework offre un ampio controllo sulla rappresentazione di stringa dei valori numerici e supporta le funzionalità seguenti per la personalizzazione del formato di tali valori:  
  
- Stringhe in formato numerico standard, che forniscono un insieme predefinito di formati per la conversione dei numeri nella rispettiva rappresentazione di stringa. È possibile usarle con qualsiasi metodo di formattazione numerica, ad esempio <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>, che include un parametro `format`. Per informazioni dettagliate, vedere [Stringhe di formato numerico standard](standard-numeric-format-strings.md).  
  
- Stringhe in formato numerico personalizzato che forniscono un insieme di simboli che possono essere combinati per definire identificatori di formato numerico personalizzato. È anche possibile usarle con qualsiasi metodo di formattazione numerica, ad esempio <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>, che include un parametro `format`. Per informazioni dettagliate, vedere [Stringhe in formato numerico personalizzato](custom-numeric-format-strings.md).  
  
- Oggetti <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo> personalizzati, che definiscono i simboli e i modelli di formato usati per la visualizzazione delle rappresentazioni di stringa di valori numerici. È possibile usarle con qualsiasi metodo di formattazione numerica, ad esempio <xref:System.Int32.ToString%2A>, che include un parametro `provider`. In genere, il parametro `provider` viene usato per specificare un formato specifico delle impostazioni cultura.  
  
 In alcuni casi, ad esempio quando un'applicazione deve visualizzare un numero di account formattato, un numero di identificazione o un codice postale, queste tre tecniche non sono adatte. .NET Framework consente anche di definire un oggetto di formattazione diverso da un oggetto <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo> per determinare come viene formattato un valore numerico. In questo argomento sono contenute istruzioni dettagliate per l'implementazione di tale oggetto ed è anche riportato un esempio di formattazione di numeri di telefono.  
  
### <a name="to-define-a-custom-format-provider"></a>Per definire un provider di formato personalizzato  
  
1. Definire una classe che implementa le interfacce <xref:System.IFormatProvider> e <xref:System.ICustomFormatter>.  
  
2. Implementare il metodo <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>. <xref:System.IFormatProvider.GetFormat%2A> è un metodo di callback richiamato dal metodo di formattazione, ad esempio il metodo <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, per recuperare l'oggetto effettivamente responsabile della formattazione personalizzata. Una tipica implementazione di <xref:System.IFormatProvider.GetFormat%2A> esegue le operazioni seguenti:  
  
    1. Determina se l'oggetto <xref:System.Type> passato come parametro del metodo rappresenta un'interfaccia <xref:System.ICustomFormatter>.  
  
    2. Se il parametro non rappresenta l'interfaccia <xref:System.ICustomFormatter>, <xref:System.IFormatProvider.GetFormat%2A> restituisce un oggetto che implementa l'interfaccia <xref:System.ICustomFormatter> responsabile della formattazione personalizzata. In genere, l'oggetto di formattazione personalizzata restituisce se stesso.  
  
    3. Se il parametro non rappresenta l'interfaccia <xref:System.ICustomFormatter>, <xref:System.IFormatProvider.GetFormat%2A> restituisce `null`.  
  
3. Implementare il metodo <xref:System.ICustomFormatter.Format%2A>. Questo metodo viene chiamato dal metodo <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> ed è responsabile della restituzione della rappresentazione di stringa di un numero. L'implementazione del metodo in genere implica le attività seguenti:  
  
    1. Facoltativamente, è possibile verificare che il metodo sia legittimamente responsabile di fornire servizi di formattazione esaminando il parametro `provider`. Per la formattazione di oggetti che implementano sia <xref:System.IFormatProvider> sia <xref:System.ICustomFormatter>, questa operazione comporta l'esecuzione di test sul parametro `provider` per verificarne l'uguaglianza all'oggetto di formattazione corrente.  
  
    2. Stabilire se l'oggetto di formattazione deve supportare identificatori di formato personalizzato. Ad esempio, un identificatore di formato "N" potrebbe indicare che un numero di telefono degli Stati Uniti deve essere restituito in formato NANP e un "I" potrebbe indicare l'output in formato ITU-T Recommendation E. 123. Se vengono utilizzati identificatori di formato, il metodo deve gestire l'identificatore di formato specifico. Quest'ultimo viene passato al metodo nel parametro `format`. Se non è disponibile alcun identificatore, il valore del parametro `format` è <xref:System.String.Empty?displayProperty=nameWithType>.  
  
    3. Recuperare il valore numerico passato al metodo come parametro `arg`. Eseguire le eventuali modifiche necessarie per convertirlo nella relativa rappresentazione di stringa.  
  
    4. Restituire la rappresentazione di stringa del parametro `arg`.  
  
### <a name="to-use-a-custom-numeric-formatting-object"></a>Per usare un oggetto di formattazione numerica personalizzata  
  
1. Creare una nuova istanza della classe di formattazione personalizzata.  
  
2. Chiamare il metodo di formattazione <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, passandovi l'oggetto di formattazione personalizzato, l'identificatore di formattazione (o <xref:System.String.Empty?displayProperty=nameWithType> se non è specificato alcun identificatore) e il valore numerico da formattare.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definito un provider di formato numerico personalizzato denominato `TelephoneFormatter` che converte un numero che rappresenta un numero telefonico degli Stati Uniti nel suo formato NANP oppure E.123. Il metodo gestisce due identificatori di formato, "N" (che restituisce il formato NANP) e "I" (che restituisce il formato E.123 internazionale).  
  
 [!code-csharp[Formatting.HowTo.NumericValue#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#1)]
 [!code-vb[Formatting.HowTo.NumericValue#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#1)]  
  
 Il provider di formati numerici personalizzati può essere usato solo con il metodo <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>. Gli altri overload di metodi di formattazione numerica, come `ToString`, che includono un parametro di tipo <xref:System.IFormatProvider>, passano tutti l'implementazione <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> di un oggetto <xref:System.Type> che rappresenta il tipo <xref:System.Globalization.NumberFormatInfo>. In cambio, si aspettano che il metodo restituisca un oggetto <xref:System.Globalization.NumberFormatInfo>. In caso contrario, il provider di formati numerici personalizzati viene ignorato e al suo posto viene usato l'oggetto <xref:System.Globalization.NumberFormatInfo> per le impostazioni cultura correnti. Nell'esempio il metodo `TelephoneFormatter.GetFormat` gestisce la possibilità di essere passato erroneamente a un metodo di formattazione numerica esaminando il parametro del metodo e restituendo `null` se rappresenta un tipo diverso da <xref:System.ICustomFormatter>.  
  
 Se un provider di formati numerici personalizzati supporta un set di identificatori di formato, assicurarsi di specificare un comportamento predefinito, nel caso in cui non venga fornito alcun identificatore di formato nell'elemento di formato usato nella chiamata al metodo <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>. Nell'esempio "N" è l'identificatore di formato predefinito. È pertanto possibile convertire un numero in un numero di telefono formattato specificando un identificatore di formato esplicito. Nell'esempio riportato di seguito viene illustrata questa chiamata al metodo.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#2)]
 [!code-vb[Formatting.HowTo.NumericValue#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#2)]  
  
 L'esecuzione della conversione è possibile anche in assenza di identificatori di formato. Nell'esempio riportato di seguito viene illustrata questa chiamata al metodo.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#3)]
 [!code-vb[Formatting.HowTo.NumericValue#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#3)]  
  
 Se non è definito alcun identificatore di formato predefinito, l'implementazione del metodo <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> deve includere codice come quello riportato di seguito in modo da permettere a .NET di fornire la formattazione non supportata dal codice.  
  
 [!code-csharp[System.ICustomFormatter.Format#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.ICustomFormatter.Format/cs/format.cs#1)]
 [!code-vb[System.ICustomFormatter.Format#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.ICustomFormatter.Format/vb/Format.vb#1)]  
  
 In questo esempio il metodo che implementa <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> ha lo scopo di fungere da metodo di callback per il metodo <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>. Di conseguenza, il metodo esamina il parametro `formatProvider` per determinare se contiene un riferimento all'oggetto `TelephoneFormatter` corrente. Il metodo può tuttavia essere chiamato anche direttamente dal codice. In questo caso, è possibile usare il parametro `formatProvider` per specificare un oggetto <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo> che fornisce informazioni di formattazione specifiche delle impostazioni cultura.
