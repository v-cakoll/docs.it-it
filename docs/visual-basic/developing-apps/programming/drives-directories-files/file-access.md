---
title: Accesso ai file
ms.date: 07/20/2015
helpviewer_keywords:
- file access
- files [Visual Basic], input and output
- file access, Visual Basic
- files [Visual Basic], I/O
- file I/O classes
- data [Visual Basic], accessing from files
- files [Visual Basic], accessing
- file access, using components
- My.Computer.FileSystem object, accessing files
- I/O [Visual Basic]
- sequential access
ms.assetid: 231533bf-d049-4345-befa-3fb78fe6517d
ms.openlocfilehash: 3b2042862ae81a52d62374e35a456766ed47edc9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401732"
---
# <a name="file-access-with-visual-basic"></a><span data-ttu-id="6dbc5-102">Accesso ai file con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6dbc5-102">File Access with Visual Basic</span></span>

<span data-ttu-id="6dbc5-103">L'oggetto `My.Computer.FileSystem` offre gli strumenti per l'uso di file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-103">The `My.Computer.FileSystem` object provides tools for working with files and folders.</span></span> <span data-ttu-id="6dbc5-104">Le proprietà, metodi ed eventi consentono di creare, copiare, spostare, analizzare ed eliminare file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-104">Its properties, methods, and events allow you to create, copy, move, investigate, and delete files and folders.</span></span> <span data-ttu-id="6dbc5-105">`My.Computer.FileSystem` offre prestazioni migliori rispetto alle funzioni legacy (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput` e così via) offerte da Visual Basic per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-105">`My.Computer.FileSystem` provides better performance than the legacy functions (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput`, etc.) that are provided by Visual Basic for backward compatibility.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6dbc5-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6dbc5-106">In This Section</span></span>  

 [<span data-ttu-id="6dbc5-107">Lettura da file</span><span class="sxs-lookup"><span data-stu-id="6dbc5-107">Reading from Files</span></span>](reading-from-files.md)  
 <span data-ttu-id="6dbc5-108">Vengono elencati gli argomenti relativi all'uso dell'oggetto `My.Computer.FileSystem` per la lettura da file</span><span class="sxs-lookup"><span data-stu-id="6dbc5-108">Lists topics dealing with using the `My.Computer.FileSystem` object to read from files</span></span>  
  
 [<span data-ttu-id="6dbc5-109">Scrittura in file</span><span class="sxs-lookup"><span data-stu-id="6dbc5-109">Writing to Files</span></span>](writing-to-files.md)  
 <span data-ttu-id="6dbc5-110">Vengono elencati gli argomenti relativi all'uso dell'oggetto `My.Computer.FileSystem` per la scrittura su file</span><span class="sxs-lookup"><span data-stu-id="6dbc5-110">Lists topics dealing with using the `My.Computer.FileSystem` object to write to files</span></span>  
  
 [<span data-ttu-id="6dbc5-111">Creazione, eliminazione e spostamento di file e directory</span><span class="sxs-lookup"><span data-stu-id="6dbc5-111">Creating, Deleting, and Moving Files and Directories</span></span>](creating-deleting-and-moving-files-and-directories.md)  
 <span data-ttu-id="6dbc5-112">Vengono elencati gli argomenti relativi all'uso dell'oggetto `My.Computer.FileSystem` per creare, copiare, eliminare e spostare file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-112">Lists topics dealing with using the `My.Computer.FileSystem` object to creating, copying, deleting and moving files and folders.</span></span>  
  
 [<span data-ttu-id="6dbc5-113">Analisi dei file di testo con l'oggetto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="6dbc5-113">Parsing Text Files with the TextFieldParser Object</span></span>](parsing-text-files-with-the-textfieldparser-object.md)  
 <span data-ttu-id="6dbc5-114">Viene illustrato come usare il `TextFieldReader` per analizzare i file di testo, ad esempio i log.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-114">Discusses how to use the `TextFieldReader` to parse text files such as logs.</span></span>  
  
 [<span data-ttu-id="6dbc5-115">Codifiche dei file</span><span class="sxs-lookup"><span data-stu-id="6dbc5-115">File Encodings</span></span>](file-encodings.md)  
 <span data-ttu-id="6dbc5-116">Vengono descritte le codifiche dei file e il relativo uso.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-116">Describes file encodings and their use.</span></span>  
  
 [<span data-ttu-id="6dbc5-117">Procedura dettagliata: Modifica di file e directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6dbc5-117">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](walkthrough-manipulating-files-and-directories.md)  
 <span data-ttu-id="6dbc5-118">Viene illustrato come creare un'utilità che specifica informazioni su file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-118">Demonstrates how to create a utility that reports information about files and folders.</span></span>  
  
 [<span data-ttu-id="6dbc5-119">Risoluzione dei problemi: Lettura e scrittura nei file di testo</span><span class="sxs-lookup"><span data-stu-id="6dbc5-119">Troubleshooting: Reading from and Writing to Text Files</span></span>](troubleshooting-reading-from-and-writing-to-text-files.md)  
 <span data-ttu-id="6dbc5-120">Vengono elencati i problemi comuni riscontrati durante la lettura e scrittura nei file di testo e le relative soluzioni.</span><span class="sxs-lookup"><span data-stu-id="6dbc5-120">Lists common problems encountered when reading and writing to text files, and suggests remedies for each.</span></span>
