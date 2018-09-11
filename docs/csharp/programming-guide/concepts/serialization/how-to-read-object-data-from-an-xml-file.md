---
title: 'Procedura: Leggere dati oggetto in un file XML (C#)'
ms.date: 07/20/2015
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
ms.openlocfilehash: 7c3bad56c6a0bee51262586aea4ce97ff0491f24
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083936"
---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a><span data-ttu-id="7c7c6-102">Procedura: Leggere dati oggetto in un file XML (C#)</span><span class="sxs-lookup"><span data-stu-id="7c7c6-102">How to: Read Object Data from an XML File (C#)</span></span>
<span data-ttu-id="7c7c6-103">Questo esempio legge i dati oggetto scritti in precedenza in un file XML usando la classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c7c6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7c7c6-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="7c7c6-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7c7c6-105">Compiling the Code</span></span>  
 <span data-ttu-id="7c7c6-106">Sostituire il nome di file "c:\temp\SerializationOverview.xml" con il nome del file contenente i dati serializzati.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="7c7c6-107">Per altre informazioni sulla serializzazione dei dati, vedere [Procedura: Scrivere i dati di un oggetto in un file XML (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="7c7c6-107">For more information about serializing data, see [How to: Write Object Data to an XML File (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="7c7c6-108">La classe deve avere un costruttore public senza parametri.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="7c7c6-109">Solo le proprietà e i campi pubblici vengono deserializzati.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7c7c6-110">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="7c7c6-110">Robust Programming</span></span>  
 <span data-ttu-id="7c7c6-111">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="7c7c6-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="7c7c6-112">La classe da serializzare non ha un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="7c7c6-113">I dati nel file non rappresentano i dati della classe da deserializzare.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
-   <span data-ttu-id="7c7c6-114">Il file non esiste (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="7c7c6-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7c7c6-115">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7c7c6-115">.NET Framework Security</span></span>  
 <span data-ttu-id="7c7c6-116">Verificare sempre gli input e non deserializzare mai i dati proveniente da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="7c7c6-117">L'oggetto ricreato viene eseguito in un computer locale con le autorizzazioni del codice che ha eseguito la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="7c7c6-118">Prima di usare i dati nell'applicazione verificare tutti gli input.</span><span class="sxs-lookup"><span data-stu-id="7c7c6-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c7c6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c7c6-119">See Also</span></span>

- <xref:System.IO.StreamWriter>  
- [<span data-ttu-id="7c7c6-120">Procedura: Scrivere dati oggetto in un file XML (C#)</span><span class="sxs-lookup"><span data-stu-id="7c7c6-120">How to: Write Object Data to an XML File (C#)</span></span>](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)  
- [<span data-ttu-id="7c7c6-121">Serializzazione (C#)</span><span class="sxs-lookup"><span data-stu-id="7c7c6-121">Serialization (C#)</span></span>](../../../../csharp/programming-guide/concepts/serialization/index.md)  
- [<span data-ttu-id="7c7c6-122">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7c7c6-122">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
