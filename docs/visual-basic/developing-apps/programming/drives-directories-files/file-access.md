---
title: Accesso ai file con Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2aabea79e3c7a6dabf47647c7e27b072738ba363
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="file-access-with-visual-basic"></a><span data-ttu-id="1e08e-102">Accesso ai file con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e08e-102">File Access with Visual Basic</span></span>
<span data-ttu-id="1e08e-103">L'oggetto `My.Computer.FileSystem` offre gli strumenti per l'uso di file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="1e08e-103">The `My.Computer.FileSystem` object provides tools for working with files and folders.</span></span> <span data-ttu-id="1e08e-104">Le proprietà, metodi ed eventi consentono di creare, copiare, spostare, analizzare ed eliminare file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="1e08e-104">Its properties, methods, and events allow you to create, copy, move, investigate, and delete files and folders.</span></span> <span data-ttu-id="1e08e-105">`My.Computer.FileSystem` offre prestazioni migliori rispetto alle funzioni legacy (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput` e così via) offerte da Visual Basic per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="1e08e-105">`My.Computer.FileSystem` provides better performance than the legacy functions (`FileOpen`, `FileClose`, `Input`, `InputString`, `LineInput`, etc.) that are provided by Visual Basic for backward compatibility.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e08e-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="1e08e-106">In This Section</span></span>  
 [<span data-ttu-id="1e08e-107">Lettura da file</span><span class="sxs-lookup"><span data-stu-id="1e08e-107">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 <span data-ttu-id="1e08e-108">Vengono elencati gli argomenti relativi all'uso dell'oggetto `My.Computer.FileSystem` per la lettura da file</span><span class="sxs-lookup"><span data-stu-id="1e08e-108">Lists topics dealing with using the `My.Computer.FileSystem` object to read from files</span></span>  
  
 [<span data-ttu-id="1e08e-109">Scrittura su file</span><span class="sxs-lookup"><span data-stu-id="1e08e-109">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 <span data-ttu-id="1e08e-110">Vengono elencati gli argomenti relativi all'uso dell'oggetto `My.Computer.FileSystem` per la scrittura su file</span><span class="sxs-lookup"><span data-stu-id="1e08e-110">Lists topics dealing with using the `My.Computer.FileSystem` object to write to files</span></span>  
  
 [<span data-ttu-id="1e08e-111">Creazione, eliminazione e spostamento di file e directory</span><span class="sxs-lookup"><span data-stu-id="1e08e-111">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)  
 <span data-ttu-id="1e08e-112">Vengono elencati gli argomenti relativi all'uso dell'oggetto `My.Computer.FileSystem` per creare, copiare, eliminare e spostare file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="1e08e-112">Lists topics dealing with using the `My.Computer.FileSystem` object to creating, copying, deleting and moving files and folders.</span></span>  
  
 [<span data-ttu-id="1e08e-113">Analisi dei file di testo con l'oggetto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="1e08e-113">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 <span data-ttu-id="1e08e-114">Viene illustrato come usare il `TextFieldReader` per analizzare i file di testo, ad esempio i log.</span><span class="sxs-lookup"><span data-stu-id="1e08e-114">Discusses how to use the `TextFieldReader` to parse text files such as logs.</span></span>  
  
 [<span data-ttu-id="1e08e-115">Codifiche dei file</span><span class="sxs-lookup"><span data-stu-id="1e08e-115">File Encodings</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 <span data-ttu-id="1e08e-116">Vengono descritte le codifiche dei file e il relativo uso.</span><span class="sxs-lookup"><span data-stu-id="1e08e-116">Describes file encodings and their use.</span></span>  
  
 [<span data-ttu-id="1e08e-117">Procedura dettagliata: Modifica di file e directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e08e-117">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 <span data-ttu-id="1e08e-118">Viene illustrato come creare un'utilità che specifica informazioni su file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="1e08e-118">Demonstrates how to create a utility that reports information about files and folders.</span></span>  
  
 [<span data-ttu-id="1e08e-119">Risoluzione dei problemi: lettura e scrittura nei file di testo</span><span class="sxs-lookup"><span data-stu-id="1e08e-119">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 <span data-ttu-id="1e08e-120">Vengono elencati i problemi comuni riscontrati durante la lettura e scrittura nei file di testo e le relative soluzioni.</span><span class="sxs-lookup"><span data-stu-id="1e08e-120">Lists common problems encountered when reading and writing to text files, and suggests remedies for each.</span></span>
