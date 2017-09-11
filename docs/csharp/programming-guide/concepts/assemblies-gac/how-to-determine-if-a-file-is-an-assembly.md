---
title: "Procedura: Determinare se un file è un assembly (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ee402e28374040ab22173788dce421345b2ef3b5
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-determine-if-a-file-is-an-assembly-c"></a><span data-ttu-id="0b77e-102">Procedura: Determinare se un file è un assembly (C#)</span><span class="sxs-lookup"><span data-stu-id="0b77e-102">How to: Determine If a File Is an Assembly (C#)</span></span>
<span data-ttu-id="0b77e-103">Un file è un assembly unicamente nei casi in cui è gestito e include nei metadati una voce assembly.</span><span class="sxs-lookup"><span data-stu-id="0b77e-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="0b77e-104">Per altre informazioni sugli assembly e sui metadati, vedere l'argomento [Manifesto dell'assembly](https://msdn.microsoft.com/library/1w45z383).</span><span class="sxs-lookup"><span data-stu-id="0b77e-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](https://msdn.microsoft.com/library/1w45z383).</span></span>  
  
### <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="0b77e-105">Procedura: Determinare se un file è un assembly in modo manuale</span><span class="sxs-lookup"><span data-stu-id="0b77e-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="0b77e-106">Avviare il [Disassembler IL (Ildasm.exe)](https://msdn.microsoft.com/library/f7dy01k1).</span><span class="sxs-lookup"><span data-stu-id="0b77e-106">Start the [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1).</span></span>  
  
2.  <span data-ttu-id="0b77e-107">Caricare il file che si intende verificare.</span><span class="sxs-lookup"><span data-stu-id="0b77e-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="0b77e-108">Se **ILDASM** segnala che il file non è un file eseguibile portabile (PE, portable executable), tale file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="0b77e-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="0b77e-109">Per altre informazioni, vedere [Procedura: Visualizzare il contenuto dell'assembly](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span><span class="sxs-lookup"><span data-stu-id="0b77e-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
### <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="0b77e-110">Procedura: Determinare se un file è un assembly a livello di codice</span><span class="sxs-lookup"><span data-stu-id="0b77e-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="0b77e-111">Chiamare il metodo <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>, passando il percorso file completo e il nome del file sottoposto a test.</span><span class="sxs-lookup"><span data-stu-id="0b77e-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="0b77e-112">Se viene generata un'eccezione <xref:System.BadImageFormatException>, il file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="0b77e-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b77e-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b77e-113">Example</span></span>  
 <span data-ttu-id="0b77e-114">Nell'esempio riportato di seguito viene testata una DLL per verificare se è un assembly.</span><span class="sxs-lookup"><span data-stu-id="0b77e-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
```  
class TestAssembly  
{  
    static void Main()  
    {  
  
        try  
        {  
            System.Reflection.AssemblyName testAssembly =  
                System.Reflection.AssemblyName.GetAssemblyName(@"C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll");  
  
            System.Console.WriteLine("Yes, the file is an assembly.");  
        }  
  
        catch (System.IO.FileNotFoundException)  
        {  
            System.Console.WriteLine("The file cannot be found.");  
        }  
  
        catch (System.BadImageFormatException)  
        {  
            System.Console.WriteLine("The file is not an assembly.");  
        }  
  
        catch (System.IO.FileLoadException)  
        {  
            System.Console.WriteLine("The assembly has already been loaded.");  
        }  
    }  
}  
/* Output (with .NET Framework 3.5 installed):  
    Yes, the file is an assembly.  
*/  
```  
  
 <span data-ttu-id="0b77e-115">Il metodo <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> carica il file di test e lo rilascia dopo aver letto le informazioni.</span><span class="sxs-lookup"><span data-stu-id="0b77e-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b77e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b77e-116">See Also</span></span>  
 <span data-ttu-id="0b77e-117"><xref:System.Reflection.AssemblyName></span><span class="sxs-lookup"><span data-stu-id="0b77e-117"><xref:System.Reflection.AssemblyName></span></span>   
 <span data-ttu-id="0b77e-118">[Guida per programmatori C#](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0b77e-118">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="0b77e-119">Assembly e Global Assembly Cache (C#)</span><span class="sxs-lookup"><span data-stu-id="0b77e-119">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)

