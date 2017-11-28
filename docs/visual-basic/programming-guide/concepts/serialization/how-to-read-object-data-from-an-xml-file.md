---
title: 'Procedura: leggere dati oggetto in un File XML (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47e5c614f2083ec2c595bba9c9454ecc5f61c786
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a><span data-ttu-id="e1556-102">Procedura: leggere dati oggetto in un File XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1556-102">How to: Read Object Data from an XML File (Visual Basic)</span></span>
<span data-ttu-id="e1556-103">Questo esempio legge i dati oggetto scritti in precedenza in un file XML usando la classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="e1556-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1556-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1556-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="e1556-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e1556-105">Compiling the Code</span></span>  
 <span data-ttu-id="e1556-106">Sostituire il nome di file "c:\temp\SerializationOverview.xml" con il nome del file contenente i dati serializzati.</span><span class="sxs-lookup"><span data-stu-id="e1556-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="e1556-107">Per ulteriori informazioni sulla serializzazione dei dati, vedere [procedura: scrivere dati oggetto in un File XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="e1556-107">For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="e1556-108">La classe deve avere un costruttore public senza parametri.</span><span class="sxs-lookup"><span data-stu-id="e1556-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="e1556-109">Solo le proprietà e i campi pubblici vengono deserializzati.</span><span class="sxs-lookup"><span data-stu-id="e1556-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e1556-110">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="e1556-110">Robust Programming</span></span>  
 <span data-ttu-id="e1556-111">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="e1556-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="e1556-112">La classe da serializzare non ha un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="e1556-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="e1556-113">I dati nel file non rappresentano i dati della classe da deserializzare.</span><span class="sxs-lookup"><span data-stu-id="e1556-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
-   <span data-ttu-id="e1556-114">Il file non esiste (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="e1556-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e1556-115">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e1556-115">.NET Framework Security</span></span>  
 <span data-ttu-id="e1556-116">Verificare sempre gli input e non deserializzare mai i dati proveniente da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="e1556-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="e1556-117">L'oggetto ricreato viene eseguito in un computer locale con le autorizzazioni del codice che ha eseguito la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="e1556-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="e1556-118">Prima di usare i dati nell'applicazione verificare tutti gli input.</span><span class="sxs-lookup"><span data-stu-id="e1556-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1556-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1556-119">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 [<span data-ttu-id="e1556-120">Procedura: Scrivere dati oggetto in un file XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1556-120">How to: Write Object Data to an XML File (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)  
 [<span data-ttu-id="e1556-121">Serializzazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1556-121">Serialization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/index.md)  
 [<span data-ttu-id="e1556-122">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1556-122">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
