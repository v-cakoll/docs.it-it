---
title: 'Procedura: Eseguire trasformazioni del flusso di testo in XML (C#)'
ms.date: 07/20/2015
ms.assetid: 9b3bd941-d0ff-4f2d-ae41-7c3b81d8fae6
ms.openlocfilehash: 6dc48a7342bbeedb79e8e7f4a9270899be336f91
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70851030"
---
# <a name="how-to-perform-streaming-transformations-of-text-to-xml-c"></a>Procedura: Eseguire trasformazioni del flusso di testo in XML (C#)

Uno degli approcci disponibili per l'elaborazione di un file di testo consiste nello scrivere un metodo di estensione che genera un flusso del file di testo, una riga alla volta, tramite il costrutto `yield return`. È quindi possibile scrivere una query LINQ che elabora il file di testo in modo posticipato lazy. Se poi si usa <xref:System.Xml.Linq.XStreamingElement> per il flusso di output, è possibile creare una trasformazione del file di testo in XML che usa una quantità minima di memoria, indipendentemente dalle dimensioni del file di testo di origine.

 È necessario tener conto di alcune considerazioni in relazione alle trasformazioni di flusso. Le trasformazioni di flusso sono ideali nelle situazioni in cui è possibile elaborare l'intero file una sola volta e se è possibile elaborare le righe nell'ordine in cui sono riportate nel documento di origine. Se è necessario elaborare il file più volte o ordinare le righe prima che sia possibile elaborarle, si perderanno molti dei vantaggi associati all'utilizzo di una tecnica di flusso.

## <a name="example"></a>Esempio

 Il file di testo seguente, People.txt, è l'origine di questo esempio.

```text
#This is a comment
1,Tai,Yee,Writer
2,Nikolay,Grachev,Programmer
3,David,Wright,Inventor
```

 Nel codice seguente è contenuto un metodo di estensione che genera il flusso delle righe del file di testo in modo posticipato.

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

 Questo esempio produce il seguente output:

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

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XStreamingElement>
