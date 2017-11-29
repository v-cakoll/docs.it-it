---
title: "Elaborazione di unità, directory e file (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- drives
- drives, processing
- Visual Basic code, file access
- files [Visual Basic], processing
- files [Visual Basic], accessing
- directories [Visual Studio], processing
ms.assetid: f1db14c8-a4fd-4d0b-8323-c7cb29d688c2
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 27a5c3c389860cdc29c4263edbff492738ffe565
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="processing-drives-directories-and-files-visual-basic"></a><span data-ttu-id="1f013-102">Elaborazione di unità, directory e file (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f013-102">Processing Drives, Directories, and Files (Visual Basic)</span></span>
<span data-ttu-id="1f013-103">È possibile usare [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] per elaborare unità, cartelle e file con l'oggetto `My.Computer.FileSystem` che offre prestazioni migliori ed è più semplice da usare rispetto ai metodi tradizionali, ad esempio le funzioni `FileOpen` e `Write`, che sono tuttavia ancora disponibili.</span><span class="sxs-lookup"><span data-stu-id="1f013-103">You can use [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to process drives, folders, and files with the `My.Computer.FileSystem` object, which provides better performance and is easier to use than traditional methods such as the `FileOpen` and `Write` functions (although they are still available).</span></span> <span data-ttu-id="1f013-104">Le sezioni seguenti descrivono questi metodi in dettaglio.</span><span class="sxs-lookup"><span data-stu-id="1f013-104">The following sections discuss these methods in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f013-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1f013-105">In This Section</span></span>  
 [<span data-ttu-id="1f013-106">Accesso ai file con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f013-106">File Access with Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 <span data-ttu-id="1f013-107">Descrive come usare l'oggetto `My.Computer.FileSystem` per lavorare con file, unità e cartelle.</span><span class="sxs-lookup"><span data-stu-id="1f013-107">Discusses how to use the `My.Computer.FileSystem` object to work with files, drives, and folders.</span></span>  
  
 [<span data-ttu-id="1f013-108">Nozioni fondamentali sul file system e sulla funzionalità di I/O di file di .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f013-108">Basics of .NET Framework File I/O and the File System (Visual Basic)</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)  
 <span data-ttu-id="1f013-109">Offre una panoramica dei concetti relativi alla funzionalità di I/O di file in .NET Framework, inclusi flussi, spazio di memorizzazione isolato, eventi di file, attributi di file e accesso ai file.</span><span class="sxs-lookup"><span data-stu-id="1f013-109">Provides an overview of file I/O concepts in the .NET Framework, including streams, isolated storage, file events, file attributes, and file access.</span></span>  
  
 [<span data-ttu-id="1f013-110">Procedura dettagliata: Modifica di file mediante i metodi .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1f013-110">Walkthrough: Manipulating Files by Using .NET Framework Methods</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)  
 <span data-ttu-id="1f013-111">Descrive come usare [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] per modificare file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="1f013-111">Demonstrates how to use the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] to manipulate files and folders.</span></span>  
  
 [<span data-ttu-id="1f013-112">Procedura dettagliata: modifica di file e directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f013-112">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 <span data-ttu-id="1f013-113">Descrive come usare l'oggetto `My.Computer.FileSystem` per modificare file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="1f013-113">Demonstrates how to use the `My.Computer.FileSystem` object to manipulate files and folders.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1f013-114">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="1f013-114">Related Sections</span></span>  
 [<span data-ttu-id="1f013-115">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="1f013-115">Program Structure and Code Conventions</span></span>](../../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 <span data-ttu-id="1f013-116">Offre le linee guida relative alla struttura fisica e all'aspetto dei programmi.</span><span class="sxs-lookup"><span data-stu-id="1f013-116">Provides guidelines for the physical structure and appearance of programs.</span></span>  
  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <span data-ttu-id="1f013-117">Documentazione di riferimento dell'oggetto `My.Computer.FileSystem` e i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="1f013-117">Reference documentation for the `My.Computer.FileSystem` object and its members.</span></span>
