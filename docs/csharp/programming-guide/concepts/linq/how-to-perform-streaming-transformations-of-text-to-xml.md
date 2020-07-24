---
title: Come eseguire trasformazioni del flusso di testo in XML (C#)
description: Informazioni su come eseguire una trasformazione del flusso di testo in XML in C#, in cui il file di testo viene trasmesso una riga alla volta e viene usata una query LINQ per elaborare il file di testo.
ms.date: 07/20/2015
ms.assetid: 9b3bd941-d0ff-4f2d-ae41-7c3b81d8fae6
ms.openlocfilehash: f933064be70d39b59cf7dbe51b4ee92e5226647a
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104743"
---
# <a name="how-to-perform-streaming-transformations-of-text-to-xml-c"></a><span data-ttu-id="5f110-103">Come eseguire trasformazioni del flusso di testo in XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5f110-103">How to perform streaming transformations of text to XML (C#)</span></span>

<span data-ttu-id="5f110-104">Uno degli approcci disponibili per l'elaborazione di un file di testo consiste nello scrivere un metodo di estensione che genera un flusso del file di testo, una riga alla volta, tramite il costrutto `yield return`.</span><span class="sxs-lookup"><span data-stu-id="5f110-104">One approach to processing a text file is to write an extension method that streams the text file a line at a time using the `yield return` construct.</span></span> <span data-ttu-id="5f110-105">È quindi possibile scrivere una query LINQ che elabora il file di testo in modo posticipato lazy.</span><span class="sxs-lookup"><span data-stu-id="5f110-105">You then can write a LINQ query that processes the text file in a lazy deferred fashion.</span></span> <span data-ttu-id="5f110-106">Se poi si usa <xref:System.Xml.Linq.XStreamingElement> per il flusso di output, è possibile creare una trasformazione del file di testo in XML che usa una quantità minima di memoria, indipendentemente dalle dimensioni del file di testo di origine.</span><span class="sxs-lookup"><span data-stu-id="5f110-106">If you then use <xref:System.Xml.Linq.XStreamingElement> to stream output, you then can create a transformation from the text file to XML that uses a minimal amount of memory, regardless of the size of the source text file.</span></span>

 <span data-ttu-id="5f110-107">È necessario tener conto di alcune considerazioni in relazione alle trasformazioni di flusso.</span><span class="sxs-lookup"><span data-stu-id="5f110-107">There are some caveats regarding streaming transformations.</span></span> <span data-ttu-id="5f110-108">Le trasformazioni di flusso sono ideali nelle situazioni in cui è possibile elaborare l'intero file una sola volta e se è possibile elaborare le righe nell'ordine in cui sono riportate nel documento di origine.</span><span class="sxs-lookup"><span data-stu-id="5f110-108">A streaming transformation is best applied in situations where you can process the entire file once, and if you can process the lines in the order that they occur in the source document.</span></span> <span data-ttu-id="5f110-109">Se è necessario elaborare il file più volte o ordinare le righe prima che sia possibile elaborarle, si perderanno molti dei vantaggi associati all'utilizzo di una tecnica di flusso.</span><span class="sxs-lookup"><span data-stu-id="5f110-109">If you have to process the file more than once, or if you have to sort the lines before you can process them, you will lose many of the benefits of using a streaming technique.</span></span>

## <a name="example"></a><span data-ttu-id="5f110-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f110-110">Example</span></span>

 <span data-ttu-id="5f110-111">Il file di testo seguente, People.txt, è l'origine di questo esempio.</span><span class="sxs-lookup"><span data-stu-id="5f110-111">The following text file, People.txt, is the source for this example.</span></span>

```text
#This is a comment
1,Tai,Yee,Writer
2,Nikolay,Grachev,Programmer
3,David,Wright,Inventor
```

 <span data-ttu-id="5f110-112">Nel codice seguente è contenuto un metodo di estensione che genera il flusso delle righe del file di testo in modo posticipato.</span><span class="sxs-lookup"><span data-stu-id="5f110-112">The following code contains an extension method that streams the lines of the text file in a deferred fashion.</span></span>

```csharp
public static class StreamReaderSequence
{
    public static IEnumerable<string> Lines(this StreamReader source)
    {
        if (source == null)
            throw new ArgumentNullException(nameof(source));

        string line;
        while ((line = source.ReadLine()) != null)
        {
            yield return line;
        }
    }
}

class Program
{
    static void Main(string[] args)
    {
        var sr = new StreamReader("People.txt");
        var xmlTree = new XStreamingElement("Root",
            from line in sr.Lines()
            let items = line.Split(',')
            where !line.StartsWith("#")
            select new XElement("Person",
                       new XAttribute("ID", items[0]),
                       new XElement("First", items[1]),
                       new XElement("Last", items[2]),
                       new XElement("Occupation", items[3])
                   )
        );
        Console.WriteLine(xmlTree);
        sr.Close();
    }
}
```

 <span data-ttu-id="5f110-113">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="5f110-113">This example produces the following output:</span></span>

```xml
<Root>
  <Person ID="1">
    <First>Tai</First>
    <Last>Yee</Last>
    <Occupation>Writer</Occupation>
  </Person>
  <Person ID="2">
    <First>Nikolay</First>
    <Last>Grachev</Last>
    <Occupation>Programmer</Occupation>
  </Person>
  <Person ID="3">
    <First>David</First>
    <Last>Wright</Last>
    <Occupation>Inventor</Occupation>
  </Person>
</Root>
```

## <a name="see-also"></a><span data-ttu-id="5f110-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f110-114">See also</span></span>

- <xref:System.Xml.Linq.XStreamingElement>
