---
title: Come scrivere i dati di un oggetto in un file XML (C#)
ms.date: 07/20/2015
ms.assetid: 7681eb98-703d-4005-a369-26a7bca0f894
ms.openlocfilehash: 6f18ae194d2ed70f633665a29772622319ea9493
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241994"
---
# <a name="how-to-write-object-data-to-an-xml-file-c"></a><span data-ttu-id="290dd-102">Come scrivere i dati di un oggetto in un file XML (C#)</span><span class="sxs-lookup"><span data-stu-id="290dd-102">How to write object data to an XML file (C#)</span></span>
<span data-ttu-id="290dd-103">Questo esempio scrive l'oggetto da una classe in un file XML usando la classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="290dd-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="290dd-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="290dd-104">Example</span></span>  
  
```csharp  
public class XMLWrite  
{  
  
   static void Main(string[] args)  
    {  
        WriteXML();  
    }  
  
    public class Book  
    {  
        public String title;
    }  
  
    public static void WriteXML()  
    {  
        Book overview = new Book();  
        overview.title = "Serialization Overview";  
        System.Xml.Serialization.XmlSerializer writer =
            new System.Xml.Serialization.XmlSerializer(typeof(Book));  
  
        var path = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments) + "//SerializationOverview.xml";  
        System.IO.FileStream file = System.IO.File.Create(path);  
  
        writer.Serialize(file, overview);  
        file.Close();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="290dd-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="290dd-105">Compiling the Code</span></span>  
 <span data-ttu-id="290dd-106">La classe da serializzare deve avere un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="290dd-106">The class being serialized must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="290dd-107">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="290dd-107">Robust Programming</span></span>  
 <span data-ttu-id="290dd-108">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="290dd-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="290dd-109">La classe da serializzare non ha un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="290dd-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="290dd-110">Il file esiste ed è di sola lettura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="290dd-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="290dd-111">Percorso del file troppo lungo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="290dd-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="290dd-112">Il disco è pieno (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="290dd-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="290dd-113">Sicurezza .NET</span><span class="sxs-lookup"><span data-stu-id="290dd-113">.NET Security</span></span>  
 <span data-ttu-id="290dd-114">Questo esempio crea un nuovo file, se il file non esiste.</span><span class="sxs-lookup"><span data-stu-id="290dd-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="290dd-115">Se un'applicazione deve creare un file, deve avere accesso `Create` alla cartella.</span><span class="sxs-lookup"><span data-stu-id="290dd-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="290dd-116">Se il file esiste già, per l'applicazione è sufficiente l'accesso `Write`, un privilegio di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="290dd-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="290dd-117">Se possibile, è più sicuro creare il file durante la distribuzione e concedere l'accesso `Read` a un unico file, anziché l'accesso `Create` a una cartella.</span><span class="sxs-lookup"><span data-stu-id="290dd-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="290dd-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="290dd-118">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="290dd-119">Come leggere i dati di un oggetto da un file XML (C#)</span><span class="sxs-lookup"><span data-stu-id="290dd-119">How to read object data from an XML file (C#)</span></span>](./how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="290dd-120">Serializzazione (C#)</span><span class="sxs-lookup"><span data-stu-id="290dd-120">Serialization (C#)</span></span>](./index.md)
