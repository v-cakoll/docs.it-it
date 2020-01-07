---
title: 'Procedura: leggere dati oggetto in un file XML'
ms.date: 07/20/2015
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
ms.openlocfilehash: efd5fb72487c92bcccf1fc797106f93c0d2a39fc
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345986"
---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a><span data-ttu-id="78921-102">Procedura: leggere i dati di un oggetto da un file XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78921-102">How to: Read Object Data from an XML File (Visual Basic)</span></span>
<span data-ttu-id="78921-103">Questo esempio legge i dati oggetto scritti in precedenza in un file XML usando la classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="78921-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78921-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="78921-104">Example</span></span>  
  
```vb  
Public Class Book  
    Public Title As String  
End Class  
  
Public Sub ReadXML()  
    Dim reader As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
    Dim file As New System.IO.StreamReader(  
        "c:\temp\SerializationOverview.xml")  
    Dim overview As Book  
    overview = CType(reader.Deserialize(file), Book)  
    Console.WriteLine(overview.Title)  
End Sub  
```  
  
## <a name="compile-the-code"></a><span data-ttu-id="78921-105">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="78921-105">Compile the code</span></span>  
 <span data-ttu-id="78921-106">Sostituire il nome di file "c:\temp\SerializationOverview.xml" con il nome del file contenente i dati serializzati.</span><span class="sxs-lookup"><span data-stu-id="78921-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="78921-107">Per ulteriori informazioni sulla serializzazione dei dati, vedere [procedura: scrivere dati oggetto in un file XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="78921-107">For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="78921-108">La classe deve avere un costruttore public senza parametri.</span><span class="sxs-lookup"><span data-stu-id="78921-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="78921-109">Solo le proprietà e i campi pubblici vengono deserializzati.</span><span class="sxs-lookup"><span data-stu-id="78921-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="78921-110">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="78921-110">Robust Programming</span></span>  
 <span data-ttu-id="78921-111">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="78921-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="78921-112">La classe da serializzare non ha un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="78921-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="78921-113">I dati nel file non rappresentano i dati della classe da deserializzare.</span><span class="sxs-lookup"><span data-stu-id="78921-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
- <span data-ttu-id="78921-114">Il file non esiste (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="78921-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="78921-115">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="78921-115">.NET Framework Security</span></span>  
 <span data-ttu-id="78921-116">Verificare sempre gli input e non deserializzare mai i dati proveniente da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="78921-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="78921-117">L'oggetto ricreato viene eseguito in un computer locale con le autorizzazioni del codice che ha eseguito la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="78921-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="78921-118">Prima di usare i dati nell'applicazione verificare tutti gli input.</span><span class="sxs-lookup"><span data-stu-id="78921-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78921-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78921-119">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="78921-120">Procedura: Scrivere dati oggetto in un file XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78921-120">How to: Write Object Data to an XML File (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
- [<span data-ttu-id="78921-121">Serializzazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78921-121">Serialization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
- [<span data-ttu-id="78921-122">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78921-122">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
