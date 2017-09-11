---
title: "Procedura: determinare se un File è un Assembly (Visual Basic) | Documenti di Microsoft"
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
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4bd3404cbdc3b79ff92290a53574080bf197fe9d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a><span data-ttu-id="c72bb-102">Procedura: determinare se un File è un Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c72bb-102">How to: Determine If a File Is an Assembly (Visual Basic)</span></span>
<span data-ttu-id="c72bb-103">Un file è un assembly se e solo se viene gestito e contiene una voce assembly nei relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="c72bb-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="c72bb-104">Per ulteriori informazioni sugli assembly e i metadati, vedere l'argomento [manifesto dell'Assembly](https://msdn.microsoft.com/library/1w45z383).</span><span class="sxs-lookup"><span data-stu-id="c72bb-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](https://msdn.microsoft.com/library/1w45z383).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="c72bb-105">Come determinare manualmente se un file è un assembly</span><span class="sxs-lookup"><span data-stu-id="c72bb-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="c72bb-106">Avviare il [Ildasm.exe (Disassembler IL)](https://msdn.microsoft.com/library/f7dy01k1).</span><span class="sxs-lookup"><span data-stu-id="c72bb-106">Start the [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1).</span></span>  
  
2.  <span data-ttu-id="c72bb-107">Caricare il file che si desidera verificare.</span><span class="sxs-lookup"><span data-stu-id="c72bb-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="c72bb-108">Se **ILDASM** report che il file non è un file eseguibile portabile (PE), quindi non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="c72bb-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="c72bb-109">Per ulteriori informazioni, vedere l'argomento [How to: View Assembly Contents](http://msdn.microsoft.com/library/fb7baaab-4c0d-47ad-8fd3-4591cf834709).</span><span class="sxs-lookup"><span data-stu-id="c72bb-109">For more information, see the topic [How to: View Assembly Contents](http://msdn.microsoft.com/library/fb7baaab-4c0d-47ad-8fd3-4591cf834709).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="c72bb-110">Come determinare se un file è un assembly a livello di codice</span><span class="sxs-lookup"><span data-stu-id="c72bb-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="c72bb-111">Chiamare il <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>, passando il percorso completo e il nome del file di cui si sta testando.</xref:System.Reflection.AssemblyName.GetAssemblyName%2A></span><span class="sxs-lookup"><span data-stu-id="c72bb-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="c72bb-112">Se un <xref:System.BadImageFormatException>viene generata un'eccezione, il file non è un assembly.</xref:System.BadImageFormatException></span><span class="sxs-lookup"><span data-stu-id="c72bb-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c72bb-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="c72bb-113">Example</span></span>  
 <span data-ttu-id="c72bb-114">In questo esempio viene testata una DLL per verificare se si tratta di un assembly.</span><span class="sxs-lookup"><span data-stu-id="c72bb-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
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
  
 <span data-ttu-id="c72bb-115">Il <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>metodo carica il file di test e quindi lo rilascia una volta le informazioni vengono lette.</xref:System.Reflection.AssemblyName.GetAssemblyName%2A></span><span class="sxs-lookup"><span data-stu-id="c72bb-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c72bb-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c72bb-116">See Also</span></span>  
 <span data-ttu-id="c72bb-117"><xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName></span><span class="sxs-lookup"><span data-stu-id="c72bb-117"><xref:System.Reflection.AssemblyName></span></span>   
<span data-ttu-id="c72bb-118"> [Concetti di programmazione](../../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="c72bb-118"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="c72bb-119"> [Gli assembly e Global Assembly Cache (Visual Basic)](index.md)</span><span class="sxs-lookup"><span data-stu-id="c72bb-119"> [Assemblies and the Global Assembly Cache (Visual Basic)](index.md)</span></span>
