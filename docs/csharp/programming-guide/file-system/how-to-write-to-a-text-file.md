---
title: Come scrivere in un file di testo- C# Guida alla programmazione
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: ac16fb971eae5654a55e2f1753d78a6458f03315
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712247"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="17f73-102">Come scrivere in un file di testo (C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="17f73-102">How to write to a text file (C# Programming Guide)</span></span>
<span data-ttu-id="17f73-103">In questi esempi vengono mostrati vari modi per scrivere testo in un file.</span><span class="sxs-lookup"><span data-stu-id="17f73-103">These examples show various ways to write text to a file.</span></span> <span data-ttu-id="17f73-104">I primi due esempi usano metodi pratici statici nella classe <xref:System.IO.File?displayProperty=nameWithType> per scrivere ogni elemento di qualsiasi oggetto `IEnumerable<string>` e una stringa in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="17f73-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any `IEnumerable<string>` and a string to a text file.</span></span> <span data-ttu-id="17f73-105">Nell'esempio 3 viene illustrato come aggiungere testo a un file quando è necessario elaborare individualmente ogni riga mentre si scrive nel file.</span><span class="sxs-lookup"><span data-stu-id="17f73-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span> <span data-ttu-id="17f73-106">Gli esempi da 1 a 3 sovrascrivono tutto il contenuto esistente nel file, ma l'esempio 4 mostra come aggiungere il testo a un file esistente.</span><span class="sxs-lookup"><span data-stu-id="17f73-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="17f73-107">Tutti gli esempi scrivono valori letterali stringa nei file.</span><span class="sxs-lookup"><span data-stu-id="17f73-107">These examples all write string literals to files.</span></span> <span data-ttu-id="17f73-108">Per formattare il testo scritto in un file, usare il metodo <xref:System.String.Format%2A> o la funzionalità di [interpolazione di stringhe](../../language-reference/tokens/interpolated.md) di C#.</span><span class="sxs-lookup"><span data-stu-id="17f73-108">If you want to format text written to a file, use the <xref:System.String.Format%2A> method or C# [string interpolation](../../language-reference/tokens/interpolated.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17f73-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="17f73-109">Example</span></span>  
 [!code-csharp[csFilesandFolders#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="17f73-110">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="17f73-110">Robust Programming</span></span>  
 <span data-ttu-id="17f73-111">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="17f73-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="17f73-112">Il file esiste ed è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="17f73-112">The file exists and is read-only.</span></span>  
  
- <span data-ttu-id="17f73-113">Il nome del percorso è troppo lungo.</span><span class="sxs-lookup"><span data-stu-id="17f73-113">The path name may be too long.</span></span>  
  
- <span data-ttu-id="17f73-114">Il disco è pieno.</span><span class="sxs-lookup"><span data-stu-id="17f73-114">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17f73-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17f73-115">See also</span></span>

- [<span data-ttu-id="17f73-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="17f73-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="17f73-117">File system e Registro di sistema (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="17f73-117">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- [<span data-ttu-id="17f73-118">Come salvare una raccolta di oggetti personalizzati nella memoria locale</span><span class="sxs-lookup"><span data-stu-id="17f73-118">Sample: Save a collection to Application Storage</span></span>](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
