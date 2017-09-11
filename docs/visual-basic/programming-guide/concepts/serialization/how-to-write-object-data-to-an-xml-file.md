---
title: 'Procedura: scrivere dati oggetto in un File XML (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
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
ms.openlocfilehash: 27131f357c1f5afc75645bff88ae5d7cd2395617
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a><span data-ttu-id="e472f-102">Procedura: scrivere dati oggetto in un File XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e472f-102">How to: Write Object Data to an XML File (Visual Basic)</span></span>
<span data-ttu-id="e472f-103">TIl esempio scrive l'oggetto da una classe in un file XML utilizzando la <xref:System.Xml.Serialization.XmlSerializer>classe.</xref:System.Xml.Serialization.XmlSerializer></span><span class="sxs-lookup"><span data-stu-id="e472f-103">TThis example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e472f-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e472f-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="e472f-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e472f-105">Compiling the Code</span></span>  
 <span data-ttu-id="e472f-106">La classe deve avere un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="e472f-106">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e472f-107">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="e472f-107">Robust Programming</span></span>  
 <span data-ttu-id="e472f-108">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="e472f-108">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="e472f-109">La classe da serializzare non dispone di un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="e472f-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="e472f-110">Il file esiste ed è di sola lettura (<xref:System.IO.IOException>).</xref:System.IO.IOException></span><span class="sxs-lookup"><span data-stu-id="e472f-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="e472f-111">Il percorso è troppo lungo (<xref:System.IO.PathTooLongException>).</xref:System.IO.PathTooLongException></span><span class="sxs-lookup"><span data-stu-id="e472f-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="e472f-112">Il disco è pieno (<xref:System.IO.IOException>).</xref:System.IO.IOException></span><span class="sxs-lookup"><span data-stu-id="e472f-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e472f-113">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e472f-113">.NET Framework Security</span></span>  
 <span data-ttu-id="e472f-114">Questo esempio crea un nuovo file, se il file non esiste già.</span><span class="sxs-lookup"><span data-stu-id="e472f-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="e472f-115">Se un'applicazione deve creare un file, l'applicazione deve `Create` accesso per la cartella.</span><span class="sxs-lookup"><span data-stu-id="e472f-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="e472f-116">Se il file esiste già, l'applicazione deve solo `Write` accedere, un privilegio inferiore.</span><span class="sxs-lookup"><span data-stu-id="e472f-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="e472f-117">Dove possibile, è più sicuro creare il file durante la distribuzione e concedere solo `Read` accesso a un singolo file, anziché `Create` accesso per una cartella.</span><span class="sxs-lookup"><span data-stu-id="e472f-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e472f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e472f-118">See Also</span></span>  
 <span data-ttu-id="e472f-119"><xref:System.IO.StreamWriter></xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="e472f-119"><xref:System.IO.StreamWriter></span></span>   
<span data-ttu-id="e472f-120"> [Procedura: leggere dati oggetto in un File XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) </span><span class="sxs-lookup"><span data-stu-id="e472f-120"> [How to: Read Object Data from an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) </span></span>  
<span data-ttu-id="e472f-121"> [Serializzazione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)</span><span class="sxs-lookup"><span data-stu-id="e472f-121"> [Serialization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)</span></span>
