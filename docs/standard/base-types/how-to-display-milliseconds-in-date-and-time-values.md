---
title: 'Procedura: visualizzare i millisecondi nei valori data e ora'
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
- DateTime.ToString method
- displaying date and time data
- time [.NET Framework], milliseconds
- dates [.NET Framework], milliseconds
- milliseconds [.NET Framework]
ms.assetid: ae1a0610-90b9-4877-8eb6-4e30bc5e00cf
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 260d202eb0a218a6657bc719e36da6f39138e54e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-milliseconds-in-date-and-time-values"></a><span data-ttu-id="5a1d6-102">Procedura: visualizzare i millisecondi nei valori data e ora</span><span class="sxs-lookup"><span data-stu-id="5a1d6-102">How to: Display Milliseconds in Date and Time Values</span></span>
<span data-ttu-id="5a1d6-103">La data e ora predefiniti, i metodi di formattazione, ad esempio <xref:System.DateTime.ToString?displayProperty=nameWithType>, include le ore, minuti e secondi di un valore di ora ma ne esclude componente relativo ai millisecondi.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-103">The default date and time formatting methods, such as <xref:System.DateTime.ToString?displayProperty=nameWithType>, include the hours, minutes, and seconds of a time value but exclude its milliseconds component.</span></span> <span data-ttu-id="5a1d6-104">Questo argomento descrive come includere un componente millisecondi di una data e un'ora nelle stringhe di data e ora formattate.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-104">This topic shows how to include a date and time's millisecond component in formatted date and time strings.</span></span>  
  
### <a name="to-display-the-millisecond-component-of-a-datetime-value"></a><span data-ttu-id="5a1d6-105">Per visualizzare il componente millisecondi di un valore DateTime</span><span class="sxs-lookup"><span data-stu-id="5a1d6-105">To display the millisecond component of a DateTime value</span></span>  
  
1.  <span data-ttu-id="5a1d6-106">Se si usa la rappresentazione di stringa di una data, convertirla in un valore <xref:System.DateTime> o <xref:System.DateTimeOffset> tramite il metodo statico <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> o <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-106">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="5a1d6-107">Per estrarre la rappresentazione di stringa del componente di millisecondi di un'ora, chiamare il valore di data e ora <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> o <xref:System.DateTimeOffset.ToString%2A> (metodo) e passare il `fff` o `FFF` modello di formato personalizzato autonoma o con altri formato personalizzato identificatori come il `format` parametro.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-107">To extract the string representation of a time's millisecond component, call the date and time value's <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%2A> method, and pass the `fff` or `FFF` custom format pattern either alone or with other custom format specifiers as the `format` parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a1d6-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="5a1d6-108">Example</span></span>  
 <span data-ttu-id="5a1d6-109">Nell'esempio viene visualizzato il componente di millisecondi di un <xref:System.DateTime> e <xref:System.DateTimeOffset> alla console, solo sia incluso in una stringa di data e l'ora più lunga.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-109">The example displays the millisecond component of a <xref:System.DateTime> and a <xref:System.DateTimeOffset> value to the console, both alone and included in a longer date and time string.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 <span data-ttu-id="5a1d6-110">Il modello di formato `fff` include gli zeri finali nei millisecondi.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-110">The `fff` format pattern includes any trailing zeros in the millisecond value.</span></span> <span data-ttu-id="5a1d6-111">Il modello di formato `FFF` li elimina.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-111">The `FFF` format pattern suppresses them.</span></span> <span data-ttu-id="5a1d6-112">Nell'esempio seguente è illustrata questa differenza.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-112">The difference is illustrated in the following example.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 <span data-ttu-id="5a1d6-113">Uno dei problemi della definizione di un identificatore di formato personalizzato completo che include il componente millisecondi di una data e ora è rappresentato dal fatto che l'identificatore definisce un formato hardcoded che potrebbe non corrispondere alla disposizione degli elementi relativi all'ora delle impostazioni cultura correnti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-113">A problem with defining a complete custom format specifier that includes the millisecond component of a date and time is that it defines a hard-coded format that may not correspond to the arrangement of time elements in the application's current culture.</span></span> <span data-ttu-id="5a1d6-114">Un'alternativa migliore consiste nel recuperare uno della data e ora di modelli di visualizzazione definiti dalle impostazioni cultura correnti <xref:System.Globalization.DateTimeFormatInfo> dell'oggetto e modificalo per includere i millisecondi.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-114">A better alternative is to retrieve one of the date and time display patterns defined by the current culture's <xref:System.Globalization.DateTimeFormatInfo> object and modify it to include milliseconds.</span></span> <span data-ttu-id="5a1d6-115">L'esempio illustra anche questo approccio.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-115">The example also illustrates this approach.</span></span> <span data-ttu-id="5a1d6-116">Recupera le impostazioni cultura correnti completo modello di data e ora dal <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> , proprietà e quindi inserisce il modello personalizzato `.ffff` dopo il modello dei secondi.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-116">It retrieves the current culture's full date and time pattern from the <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> property, and then inserts the custom pattern `.ffff` after its seconds pattern.</span></span> <span data-ttu-id="5a1d6-117">Si noti che nell'esempio viene usata un'espressione regolare per eseguire questa operazione in una sola chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-117">Note that the example uses a regular expression to perform this operation in a single method call.</span></span>  
  
 <span data-ttu-id="5a1d6-118">È anche possibile usare un identificatore di formato personalizzato per visualizzare una parte frazionaria di secondi diversa dai millisecondi.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-118">You can also use a custom format specifier to display a fractional part of seconds other than milliseconds.</span></span> <span data-ttu-id="5a1d6-119">Ad esempio, l'identificatore di formato personalizzato `f` o `F` visualizza i decimi di secondo, l'identificatore di formato personalizzato `ff` o `FF` i centesimi di secondo e l'identificatore di formato personalizzato `ffff` o `FFFF` i decimillesimi di secondo.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-119">For example, the `f` or `F` custom format specifier displays tenths of a second, the `ff` or `FF` custom format specifier displays hundredths of a second, and the `ffff` or `FFFF` custom format specifier displays ten thousandths of a second.</span></span> <span data-ttu-id="5a1d6-120">Le parti frazionarie di un millisecondo vengono troncate anziché arrotondate nella stringa restituita.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-120">Fractional parts of a millisecond are truncated instead of rounded in the returned string.</span></span> <span data-ttu-id="5a1d6-121">Questi identificatori di formato vengono usati nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-121">These format specifiers are used in the following example.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
>  <span data-ttu-id="5a1d6-122">È possibile visualizzare piccolissime unità di secondo frazionarie, come decimillesimi di secondo o centomillesimi di secondo.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-122">It is possible to display very small fractional units of a second, such as ten thousandths of a second or hundred-thousandths of a second.</span></span> <span data-ttu-id="5a1d6-123">Questi valori tuttavia potrebbero non essere significativi.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-123">However, these values may not be meaningful.</span></span> <span data-ttu-id="5a1d6-124">La precisione dei valori di data e ora dipende dalla risoluzione del clock di sistema.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-124">The precision of date and time values depends on the resolution of the system clock.</span></span> <span data-ttu-id="5a1d6-125">In Windows NT 3.5 e versioni successive, e [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] sistemi operativi, la risoluzione del clock è di circa 10-15 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-125">On Windows NT 3.5 and later, and [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] operating systems, the clock's resolution is approximately 10-15 milliseconds.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5a1d6-126">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5a1d6-126">Compiling the Code</span></span>  
 <span data-ttu-id="5a1d6-127">Compilare il codice nella riga di comando con csc.exe o vb.exe.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-127">Compile the code at the command line using csc.exe or vb.exe.</span></span> <span data-ttu-id="5a1d6-128">Per compilare il codice in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], inserirlo in un modello di progetto applicazione console.</span><span class="sxs-lookup"><span data-stu-id="5a1d6-128">To compile the code in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], put it in a console application project template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a1d6-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a1d6-129">See Also</span></span>  
 <xref:System.Globalization.DateTimeFormatInfo>  
 [<span data-ttu-id="5a1d6-130">Custom Date and Time Format Strings</span><span class="sxs-lookup"><span data-stu-id="5a1d6-130">Custom Date and Time Format Strings</span></span>](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
