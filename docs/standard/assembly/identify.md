---
title: 'Procedura: determinare se un file è un assembly'
ms.date: 08/19/2019
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
dev_langs:
- csharp
- vb
ms.openlocfilehash: 1d66c0c166724f195a3cafd9bcbe3c7414c08ebb
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159507"
---
# <a name="how-to-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="7197d-102">Procedura: determinare se un file è un assembly</span><span class="sxs-lookup"><span data-stu-id="7197d-102">How to: Determine if a file is an assembly</span></span>

<span data-ttu-id="7197d-103">Un file è un assembly unicamente nei casi in cui è gestito e include nei metadati una voce assembly.</span><span class="sxs-lookup"><span data-stu-id="7197d-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="7197d-104">Per ulteriori informazioni sugli assembly e sui metadati, vedere [manifesto dell'assembly](manifest.md).</span><span class="sxs-lookup"><span data-stu-id="7197d-104">For more information on assemblies and metadata, see [Assembly manifest](manifest.md).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="7197d-105">Procedura: Determinare se un file è un assembly in modo manuale</span><span class="sxs-lookup"><span data-stu-id="7197d-105">How to manually determine if a file is an assembly</span></span>  
  
1. <span data-ttu-id="7197d-106">Avviare il [Disassembler IL (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="7197d-106">Start the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
2. <span data-ttu-id="7197d-107">Caricare il file che si desidera testare.</span><span class="sxs-lookup"><span data-stu-id="7197d-107">Load the file you want to test.</span></span>  
  
3. <span data-ttu-id="7197d-108">Se **ILDASM** segnala che il file non è un file eseguibile portabile (PE, portable executable), tale file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="7197d-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="7197d-109">Per ulteriori informazioni, vedere l'argomento [procedura: visualizzare il contenuto dell'assembly](view-contents.md).</span><span class="sxs-lookup"><span data-stu-id="7197d-109">For more information, see the topic [How to: View assembly contents](view-contents.md).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="7197d-110">Procedura: Determinare se un file è un assembly a livello di codice</span><span class="sxs-lookup"><span data-stu-id="7197d-110">How to programmatically determine if a file is an assembly</span></span>  
  
1. <span data-ttu-id="7197d-111">Chiamare il metodo <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType>, passando il percorso file completo e il nome del file sottoposto a test.</span><span class="sxs-lookup"><span data-stu-id="7197d-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> method, passing the full file path and name of the file you are testing.</span></span>  
  
2. <span data-ttu-id="7197d-112">Se viene generata un'eccezione <xref:System.BadImageFormatException>, il file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="7197d-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7197d-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="7197d-113">Example</span></span>  
<span data-ttu-id="7197d-114">Nell'esempio riportato di seguito viene testata una DLL per verificare se è un assembly.</span><span class="sxs-lookup"><span data-stu-id="7197d-114">This example tests a DLL to see if it is an assembly.</span></span>  

```csharp
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

```vb  
Module Module1  
    Sub Main()  
        Try  
            Dim testAssembly As Reflection.AssemblyName =  
                                Reflection.AssemblyName.GetAssemblyName("C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll")  
            Console.WriteLine("Yes, the file is an Assembly.")  
        Catch ex As System.IO.FileNotFoundException  
            Console.WriteLine("The file cannot be found.")  
        Catch ex As System.BadImageFormatException  
            Console.WriteLine("The file is not an Assembly.")  
        Catch ex As System.IO.FileLoadException  
            Console.WriteLine("The Assembly has already been loaded.")  
        End Try  
        Console.ReadLine()  
    End Sub  
End Module  
' Output (with .NET Framework 3.5 installed):  
'        Yes, the file is an Assembly.  
```

<span data-ttu-id="7197d-115">Il metodo <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> carica il file di test e lo rilascia dopo aver letto le informazioni.</span><span class="sxs-lookup"><span data-stu-id="7197d-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7197d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7197d-116">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="7197d-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7197d-117">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="7197d-118">Concetti di programmazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7197d-118">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="7197d-119">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="7197d-119">Assemblies in .NET</span></span>](index.md)
