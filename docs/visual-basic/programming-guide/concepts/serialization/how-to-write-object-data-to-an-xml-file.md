---
title: 'Procedura: scrivere dati oggetto in un file XML'
ms.date: 07/20/2015
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
ms.openlocfilehash: 989920709428f0e9cb4ddb8aeacfc71a2df220d2
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345982"
---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a><span data-ttu-id="ddd3b-102">Procedura: scrivere i dati di un oggetto in un file XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddd3b-102">How to: Write Object Data to an XML File (Visual Basic)</span></span>
<span data-ttu-id="ddd3b-103">Questo esempio scrive l'oggetto da una classe in un file XML usando la classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ddd3b-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddd3b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ddd3b-104">Example</span></span>  
  
```vb  
Public Module XMLWrite  
  
    Sub Main()  
        WriteXML()  
    End Sub  
  
    Public Class Book  
        Public Title As String  
    End Class  
  
    Public Sub WriteXML()  
        Dim overview As New Book  
        overview.Title = "Serialization Overview"  
        Dim writer As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
        Dim file As New System.IO.StreamWriter(  
            "c:\temp\SerializationOverview.xml")  
        writer.Serialize(file, overview)  
        file.Close()  
    End Sub  
End Module  
```  
  
## <a name="compile-the-code"></a><span data-ttu-id="ddd3b-105">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="ddd3b-105">Compile the code</span></span>  
 <span data-ttu-id="ddd3b-106">La classe deve avere un costruttore public senza parametri.</span><span class="sxs-lookup"><span data-stu-id="ddd3b-106">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ddd3b-107">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="ddd3b-107">Robust Programming</span></span>  
 <span data-ttu-id="ddd3b-108">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="ddd3b-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="ddd3b-109">La classe da serializzare non ha un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="ddd3b-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="ddd3b-110">Il file esiste ed è di sola lettura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="ddd3b-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="ddd3b-111">Percorso del file troppo lungo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="ddd3b-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="ddd3b-112">Il disco è pieno (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="ddd3b-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ddd3b-113">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ddd3b-113">.NET Framework Security</span></span>  
 <span data-ttu-id="ddd3b-114">Questo esempio crea un nuovo file, se il file non esiste.</span><span class="sxs-lookup"><span data-stu-id="ddd3b-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="ddd3b-115">Se un'applicazione deve creare un file, deve avere accesso `Create` alla cartella.</span><span class="sxs-lookup"><span data-stu-id="ddd3b-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="ddd3b-116">Se il file esiste già, per l'applicazione è sufficiente l'accesso `Write`, un privilegio di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="ddd3b-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="ddd3b-117">Se possibile, è più sicuro creare il file durante la distribuzione e concedere l'accesso `Read` a un unico file, anziché l'accesso `Create` a una cartella.</span><span class="sxs-lookup"><span data-stu-id="ddd3b-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddd3b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddd3b-118">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="ddd3b-119">Procedura: Leggere dati oggetto in un file XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddd3b-119">How to: Read Object Data from an XML File (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="ddd3b-120">Serializzazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddd3b-120">Serialization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
