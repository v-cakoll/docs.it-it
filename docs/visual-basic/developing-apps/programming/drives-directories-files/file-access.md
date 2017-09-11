---
title: Accesso ai file con Visual Basic
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- file access
- files, input and output
- file access, Visual Basic
- files, I/O
- file I/O classes
- data [Visual Basic], accessing from files
- files, accessing
- file access, using components
- My.Computer.FileSystem object, accessing files
- I/O [Visual Basic]
- sequential access
ms.assetid: 231533bf-d049-4345-befa-3fb78fe6517d
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 71e941bf33c3b1051c22c8170b327df9fae7d4b9
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="file-access-with-visual-basic"></a><span data-ttu-id="bdf7f-102">Accesso ai file con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdf7f-102">File Access with Visual Basic</span></span>
<span data-ttu-id="bdf7f-103">L'oggetto `My.Computer.FileSystem` offre gli strumenti per l'uso di file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="bdf7f-103">The `My.Computer.FileSystem` object provides tools for working with files and folders.</span></span> <span data-ttu-id="bdf7f-104">Le proprietà, metodi ed eventi consentono di creare, copiare, spostare, analizzare ed eliminare file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="bdf7f-104">Its properties, methods, and events allow you to create, copy, move, investigate, and delete files and folders.</span></span> <span data-ttu-id="bdf7f-105">`My.Computer.FileSystem` offre prestazioni migliori rispetto alle funzioni legacy (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput` e così via) offerte da [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="bdf7f-105">`My.Computer.FileSystem` provides better performance than the legacy functions (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput`, etc.) that are provided by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] for backward compatibility.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bdf7f-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="bdf7f-106">In This Section</span></span>  
 [<span data-ttu-id="bdf7f-107">Lettura da file</span><span class="sxs-lookup"><span data-stu-id="bdf7f-107">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 <span data-ttu-id="bdf7f-108">Vengono elencati gli argomenti relativi all'uso dell'oggetto `My.Computer.FileSystem` per la lettura da file</span><span class="sxs-lookup"><span data-stu-id="bdf7f-108">Lists topics dealing with using the `My.Computer.FileSystem` object to read from files</span></span>  
  
 [<span data-ttu-id="bdf7f-109">Scrittura su file</span><span class="sxs-lookup"><span data-stu-id="bdf7f-109">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 <span data-ttu-id="bdf7f-110">Vengono elencati gli argomenti relativi all'uso dell'oggetto `My.Computer.FileSystem` per la scrittura su file</span><span class="sxs-lookup"><span data-stu-id="bdf7f-110">Lists topics dealing with using the `My.Computer.FileSystem` object to write to files</span></span>  
  
 [<span data-ttu-id="bdf7f-111">Creazione, eliminazione e spostamento di file e directory</span><span class="sxs-lookup"><span data-stu-id="bdf7f-111">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)  
 <span data-ttu-id="bdf7f-112">Vengono elencati gli argomenti relativi all'uso dell'oggetto `My.Computer.FileSystem` per creare, copiare, eliminare e spostare file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="bdf7f-112">Lists topics dealing with using the `My.Computer.FileSystem` object to creating, copying, deleting and moving files and folders.</span></span>  
  
 [<span data-ttu-id="bdf7f-113">Analisi dei file di testo con l'oggetto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="bdf7f-113">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 <span data-ttu-id="bdf7f-114">Viene illustrato come usare il `TextFieldReader` per analizzare i file di testo, ad esempio i log.</span><span class="sxs-lookup"><span data-stu-id="bdf7f-114">Discusses how to use the `TextFieldReader` to parse text files such as logs.</span></span>  
  
 [<span data-ttu-id="bdf7f-115">Codifiche dei file</span><span class="sxs-lookup"><span data-stu-id="bdf7f-115">File Encodings</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 <span data-ttu-id="bdf7f-116">Vengono descritte le codifiche dei file e il relativo uso.</span><span class="sxs-lookup"><span data-stu-id="bdf7f-116">Describes file encodings and their use.</span></span>  
  
 [<span data-ttu-id="bdf7f-117">Procedura dettagliata: modifica di file e directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdf7f-117">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 <span data-ttu-id="bdf7f-118">Viene illustrato come creare un'utilità che specifica informazioni su file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="bdf7f-118">Demonstrates how to create a utility that reports information about files and folders.</span></span>  
  
 [<span data-ttu-id="bdf7f-119">Risoluzione dei problemi: lettura e scrittura nei file di testo</span><span class="sxs-lookup"><span data-stu-id="bdf7f-119">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 <span data-ttu-id="bdf7f-120">Vengono elencati i problemi comuni riscontrati durante la lettura e scrittura nei file di testo e le relative soluzioni.</span><span class="sxs-lookup"><span data-stu-id="bdf7f-120">Lists common problems encountered when reading and writing to text files, and suggests remedies for each.</span></span>

