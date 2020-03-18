---
title: Come leggere i dati dell'oggetto da un file XML (C
ms.date: 07/20/2015
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
ms.openlocfilehash: 18428cbe2f2d3b9434a77ee4d063ceabbba6bcb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167818"
---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a>Come leggere i dati dell'oggetto da un file XML (C
Questo esempio legge i dati oggetto scritti in precedenza in un file XML usando la classe <xref:System.Xml.Serialization.XmlSerializer>.  
  
## <a name="example"></a>Esempio  
  
```csharp  
public class Book  
{  
    public String title;  
}
  
public void ReadXML()  
{  
    // First write something so that there is something to read ...  
    var b = new Book { title = "Serialization Overview" };  
    var writer = new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    var wfile = new System.IO.StreamWriter(@"c:\temp\SerializationOverview.xml");  
    writer.Serialize(wfile, b);  
    wfile.Close();  
  
    // Now we can read the serialized book ...  
    System.Xml.Serialization.XmlSerializer reader =
        new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    System.IO.StreamReader file = new System.IO.StreamReader(  
        @"c:\temp\SerializationOverview.xml");  
    Book overview =  (Book)reader.Deserialize(file);  
    file.Close();  
  
    Console.WriteLine(overview.title);  
  
}  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
Sostituire il nome di file "c:\temp\SerializationOverview.xml" con il nome del file contenente i dati serializzati. Per ulteriori informazioni sulla serializzazione dei dati, vedere Come scrivere i [dati dell'oggetto in un file XML (Cè)](./how-to-write-object-data-to-an-xml-file.md).
  
 La classe deve avere un costruttore public senza parametri.  
  
 Solo le proprietà e i campi pubblici vengono deserializzati.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
- La classe da serializzare non ha un costruttore pubblico senza parametri.  
  
- I dati nel file non rappresentano i dati della classe da deserializzare.  
  
- Il file non esiste (<xref:System.IO.IOException>).  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Verificare sempre gli input e non deserializzare mai i dati proveniente da un'origine non attendibile. L'oggetto ricreato viene eseguito in un computer locale con le autorizzazioni del codice che ha eseguito la deserializzazione. Prima di usare i dati nell'applicazione verificare tutti gli input.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.StreamWriter>
- [Come scrivere i dati dell'oggetto in un file XML (C](./how-to-write-object-data-to-an-xml-file.md)
- [Serializzazione (C#)](./index.md)
- [Guida per programmatori C#](../../index.md)
