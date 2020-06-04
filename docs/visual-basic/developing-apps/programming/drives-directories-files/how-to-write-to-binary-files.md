---
title: 'Procedura: Scrivere in file binari'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], binary access
- WriteAllBytes method [Visual Basic]
- binary files [Visual Basic], writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
ms.openlocfilehash: b36da82060b930101cb54dd852d050ac0155bd10
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411551"
---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a><span data-ttu-id="9c36e-102">Procedura: scrivere all'interno di file binari in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9c36e-102">How to: Write to Binary Files in Visual Basic</span></span>

<span data-ttu-id="9c36e-103">Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> scrive i dati in un file binario.</span><span class="sxs-lookup"><span data-stu-id="9c36e-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> method writes data to a binary file.</span></span> <span data-ttu-id="9c36e-104">Se il parametro`append` è `True`, i dati verranno aggiunti al file; in caso contrario i dati nel file saranno sovrascritti.</span><span class="sxs-lookup"><span data-stu-id="9c36e-104">If the `append` parameter is `True`, it will append the data to the file; otherwise data in the file is overwritten.</span></span>

<span data-ttu-id="9c36e-105">Se il percorso specificato che esclude il nome file non è valido, verrà generata un'eccezione <xref:System.IO.DirectoryNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="9c36e-105">If the specified path excluding the file name is not valid, a <xref:System.IO.DirectoryNotFoundException> exception will be thrown.</span></span> <span data-ttu-id="9c36e-106">Se il percorso sia valido, ma il file non esiste, verrà creato il file.</span><span class="sxs-lookup"><span data-stu-id="9c36e-106">If the path is valid but the file does not exist, the file will be created.</span></span>

## <a name="to-write-to-a-binary-file"></a><span data-ttu-id="9c36e-107">Per scrivere in un file binario</span><span class="sxs-lookup"><span data-stu-id="9c36e-107">To write to a binary file</span></span>

<span data-ttu-id="9c36e-108">Usare il metodo `WriteAllBytes` specificando il percorso e nome file e i byte da scrivere.</span><span class="sxs-lookup"><span data-stu-id="9c36e-108">Use the `WriteAllBytes` method, supplying the file path and name and the bytes to be written.</span></span> <span data-ttu-id="9c36e-109">In questo esempio la matrice di dati `CustomerData` viene aggiunta al file denominato `CollectedData.dat`.</span><span class="sxs-lookup"><span data-stu-id="9c36e-109">This example appends the data array `CustomerData` to the file named `CollectedData.dat`.</span></span>

[!code-vb[VbVbcnMyFileSystem#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#27)]

## <a name="robust-programming"></a><span data-ttu-id="9c36e-110">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="9c36e-110">Robust Programming</span></span>

<span data-ttu-id="9c36e-111">Le condizioni seguenti possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="9c36e-111">The following conditions may create an exception:</span></span>

- <span data-ttu-id="9c36e-112">Il percorso non è valido per uno di questi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="9c36e-112">The path is not valid for one of the following reasons: it is a zero-length string; it contains only white space; or it contains invalid characters.</span></span> <span data-ttu-id="9c36e-113">(<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="9c36e-113">(<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="9c36e-114">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="9c36e-114">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="9c36e-115">`File` punta a un percorso che non esiste (<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="9c36e-115">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>

- <span data-ttu-id="9c36e-116">Il file è in uso in un altro processo oppure si verifica un errore di I/O (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="9c36e-116">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="9c36e-117">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="9c36e-117">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>

- <span data-ttu-id="9c36e-118">Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="9c36e-118">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="9c36e-119">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="9c36e-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>

## <a name="see-also"></a><span data-ttu-id="9c36e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c36e-120">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [<span data-ttu-id="9c36e-121">Procedura: Scrivere testo in file</span><span class="sxs-lookup"><span data-stu-id="9c36e-121">How to: Write Text to Files</span></span>](how-to-write-text-to-files.md)
