---
title: 'Procedura: scrivere in un file di testo (Guida per programmatori C#)'
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: ca08651bfce1a92f65a3e6fec7da3411a22bffb2
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43780075"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="5ccbb-102">Procedura: scrivere in un file di testo (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="5ccbb-102">How to: Write to a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="5ccbb-103">In questi esempi vengono mostrati vari modi per scrivere testo in un file.</span><span class="sxs-lookup"><span data-stu-id="5ccbb-103">These examples show various ways to write text to a file.</span></span> <span data-ttu-id="5ccbb-104">I primi due esempi usano metodi pratici statici nella classe <xref:System.IO.File?displayProperty=nameWithType> per scrivere ogni elemento di qualsiasi oggetto `IEnumerable<string>` e una stringa in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="5ccbb-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any `IEnumerable<string>` and a string to a text file.</span></span> <span data-ttu-id="5ccbb-105">Nell'esempio 3 viene illustrato come aggiungere testo a un file quando è necessario elaborare individualmente ogni riga mentre si scrive nel file.</span><span class="sxs-lookup"><span data-stu-id="5ccbb-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span> <span data-ttu-id="5ccbb-106">Gli esempi da 1 a 3 sovrascrivono tutto il contenuto esistente nel file, ma l'esempio 4 mostra come aggiungere il testo a un file esistente.</span><span class="sxs-lookup"><span data-stu-id="5ccbb-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="5ccbb-107">Tutti gli esempi scrivono valori letterali stringa nei file.</span><span class="sxs-lookup"><span data-stu-id="5ccbb-107">These examples all write string literals to files.</span></span> <span data-ttu-id="5ccbb-108">Per formattare il testo scritto in un file, usare il metodo <xref:System.String.Format%2A> o la funzionalità di [interpolazione di stringhe](../../../csharp/language-reference/tokens/interpolated.md) di C#.</span><span class="sxs-lookup"><span data-stu-id="5ccbb-108">If you want to format text written to a file, use the <xref:System.String.Format%2A> method or C# [string interpolation](../../../csharp/language-reference/tokens/interpolated.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ccbb-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="5ccbb-109">Example</span></span>  
 [!code-csharp[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="5ccbb-110">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="5ccbb-110">Robust Programming</span></span>  
 <span data-ttu-id="5ccbb-111">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="5ccbb-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="5ccbb-112">Il file esiste ed è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="5ccbb-112">The file exists and is read-only.</span></span>  
  
-   <span data-ttu-id="5ccbb-113">Il nome del percorso è troppo lungo.</span><span class="sxs-lookup"><span data-stu-id="5ccbb-113">The path name may be too long.</span></span>  
  
-   <span data-ttu-id="5ccbb-114">Il disco è pieno.</span><span class="sxs-lookup"><span data-stu-id="5ccbb-114">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ccbb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ccbb-115">See Also</span></span>

- [<span data-ttu-id="5ccbb-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5ccbb-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5ccbb-117">File system e Registro di sistema (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="5ccbb-117">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)  
- [<span data-ttu-id="5ccbb-118">Come salvare una raccolta di oggetti personalizzati nella memoria locale</span><span class="sxs-lookup"><span data-stu-id="5ccbb-118">Sample: Save a collection to Application Storage</span></span>](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
