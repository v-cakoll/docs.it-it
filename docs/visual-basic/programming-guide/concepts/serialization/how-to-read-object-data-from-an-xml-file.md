---
title: 'Procedura: leggere dati oggetto in un File XML (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3b9697f763a2d781c37960d46cbc7fa4536c84b4
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a><span data-ttu-id="49480-102">Procedura: leggere dati oggetto in un File XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49480-102">How to: Read Object Data from an XML File (Visual Basic)</span></span>
<span data-ttu-id="49480-103">In questo esempio legge i dati oggetto precedentemente scritti in un file XML utilizzando la <xref:System.Xml.Serialization.XmlSerializer>classe.</xref:System.Xml.Serialization.XmlSerializer></span><span class="sxs-lookup"><span data-stu-id="49480-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49480-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="49480-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="49480-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="49480-105">Compiling the Code</span></span>  
 <span data-ttu-id="49480-106">Sostituire il nome di file "c:\temp\SerializationOverview.xml" con il nome del file contenente i dati serializzati.</span><span class="sxs-lookup"><span data-stu-id="49480-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="49480-107">Per ulteriori informazioni sulla serializzazione dei dati, vedere [procedura: scrivere dati oggetto in un File XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="49480-107">For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="49480-108">La classe deve avere un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="49480-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="49480-109">Solo i campi e proprietà pubbliche vengono deserializzati.</span><span class="sxs-lookup"><span data-stu-id="49480-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="49480-110">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="49480-110">Robust Programming</span></span>  
 <span data-ttu-id="49480-111">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="49480-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="49480-112">La classe da serializzare non dispone di un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="49480-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="49480-113">I dati nel file non rappresentano i dati della classe da deserializzare.</span><span class="sxs-lookup"><span data-stu-id="49480-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
-   <span data-ttu-id="49480-114">Il file non esiste (<xref:System.IO.IOException>).</xref:System.IO.IOException></span><span class="sxs-lookup"><span data-stu-id="49480-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="49480-115">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="49480-115">.NET Framework Security</span></span>  
 <span data-ttu-id="49480-116">Verificare sempre gli input e di non deserializzare mai dati da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="49480-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="49480-117">L'oggetto ricreato viene eseguito in un computer locale con le autorizzazioni del codice che viene deserializzato.</span><span class="sxs-lookup"><span data-stu-id="49480-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="49480-118">Prima di usare i dati nell'applicazione verificare tutti gli input.</span><span class="sxs-lookup"><span data-stu-id="49480-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49480-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49480-119">See Also</span></span>  
 <span data-ttu-id="49480-120"><xref:System.IO.StreamWriter></xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="49480-120"><xref:System.IO.StreamWriter></span></span>   
<span data-ttu-id="49480-121"> [Procedura: scrivere dati oggetto in un File XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) </span><span class="sxs-lookup"><span data-stu-id="49480-121"> [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) </span></span>  
<span data-ttu-id="49480-122"> [Serializzazione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md) </span><span class="sxs-lookup"><span data-stu-id="49480-122"> [Serialization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md) </span></span>  
<span data-ttu-id="49480-123"> [Guida per programmatori Visual Basic](../../../../visual-basic/programming-guide/index.md)</span><span class="sxs-lookup"><span data-stu-id="49480-123"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md)</span></span>
