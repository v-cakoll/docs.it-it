---
title: "Procedura: determinare se un File è un Assembly (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 314c65ebfbb2aaf1acc9fad4cefa13c5f4f17cec
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a><span data-ttu-id="385c0-102">Procedura: determinare se un File è un Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="385c0-102">How to: Determine If a File Is an Assembly (Visual Basic)</span></span>
<span data-ttu-id="385c0-103">Un file è un assembly unicamente nei casi in cui è gestito e include nei metadati una voce assembly.</span><span class="sxs-lookup"><span data-stu-id="385c0-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="385c0-104">Per altre informazioni sugli assembly e sui metadati, vedere l'argomento [Manifesto dell'assembly](../../../../../docs/framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="385c0-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](../../../../../docs/framework/app-domains/assembly-manifest.md).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="385c0-105">Procedura: Determinare se un file è un assembly in modo manuale</span><span class="sxs-lookup"><span data-stu-id="385c0-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="385c0-106">Avviare il [Disassembler IL (Ildasm.exe)](https://msdn.microsoft.com/library/f7dy01k1).</span><span class="sxs-lookup"><span data-stu-id="385c0-106">Start the [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1).</span></span>  
  
2.  <span data-ttu-id="385c0-107">Caricare il file che si intende verificare.</span><span class="sxs-lookup"><span data-stu-id="385c0-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="385c0-108">Se **ILDASM** segnala che il file non è un file eseguibile portabile (PE, portable executable), tale file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="385c0-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="385c0-109">Per altre informazioni, vedere [Procedura: Visualizzare il contenuto dell'assembly](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span><span class="sxs-lookup"><span data-stu-id="385c0-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="385c0-110">Procedura: Determinare se un file è un assembly a livello di codice</span><span class="sxs-lookup"><span data-stu-id="385c0-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="385c0-111">Chiamare il metodo <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>, passando il percorso file completo e il nome del file sottoposto a test.</span><span class="sxs-lookup"><span data-stu-id="385c0-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="385c0-112">Se viene generata un'eccezione <xref:System.BadImageFormatException>, il file non è un assembly.</span><span class="sxs-lookup"><span data-stu-id="385c0-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="385c0-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="385c0-113">Example</span></span>  
 <span data-ttu-id="385c0-114">Nell'esempio riportato di seguito viene testata una DLL per verificare se è un assembly.</span><span class="sxs-lookup"><span data-stu-id="385c0-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
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
  
 <span data-ttu-id="385c0-115">Il metodo <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> carica il file di test e lo rilascia dopo aver letto le informazioni.</span><span class="sxs-lookup"><span data-stu-id="385c0-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="385c0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="385c0-116">See Also</span></span>  
 <xref:System.Reflection.AssemblyName>  
 [<span data-ttu-id="385c0-117">Nozioni di base sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="385c0-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)  
 [<span data-ttu-id="385c0-118">Assembly e Global Assembly Cache (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="385c0-118">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](index.md)
