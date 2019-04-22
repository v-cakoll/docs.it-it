---
title: 'Risoluzione dei problemi: Lettura e scrittura nei file di testo (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting file I/O
- writing text to files [Visual Basic], troubleshooting
- troubleshooting Visual Basic, text files
- I/O [Visual Basic], troubleshooting text files
- writing to files [Visual Basic], troubleshooting
- reading text files [Visual Basic], troubleshooting
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
ms.openlocfilehash: 90a04d9de2ac77c28a92d99e1fe118a1f8ecf448
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831787"
---
# <a name="troubleshooting-reading-from-and-writing-to-text-files-visual-basic"></a><span data-ttu-id="2dfa7-102">Risoluzione dei problemi: Lettura e scrittura nei file di testo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2dfa7-102">Troubleshooting: reading from and writing to text files (Visual Basic)</span></span>
<span data-ttu-id="2dfa7-103">In questo argomento vengono descritti i problemi che si riscontrano più comunemente quando si usano i file di testo e vengono suggerite le possibili soluzioni.</span><span class="sxs-lookup"><span data-stu-id="2dfa7-103">This topic discusses common problems encountered when working with text files and suggests an approach to each.</span></span>  
  
## <a name="common-problems"></a><span data-ttu-id="2dfa7-104">Problemi comuni</span><span class="sxs-lookup"><span data-stu-id="2dfa7-104">Common problems</span></span>  
 <span data-ttu-id="2dfa7-105">Alcuni dei problemi più comuni riscontrati quando si lavora con i file di testo sono le eccezioni di sicurezza, le codifiche dei file e i percorsi non validi.</span><span class="sxs-lookup"><span data-stu-id="2dfa7-105">The most common issues encountered when working with text files include security exceptions, file encodings, or invalid paths.</span></span>  
  
### <a name="security-exceptions"></a><span data-ttu-id="2dfa7-106">Eccezioni di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2dfa7-106">Security exceptions</span></span>  
 <span data-ttu-id="2dfa7-107">Un'eccezione <xref:System.Security.SecurityException> viene generata quando viene rilevato un errore di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2dfa7-107">A <xref:System.Security.SecurityException> is thrown when a security error occurs.</span></span> <span data-ttu-id="2dfa7-108">Ciò spesso è dovuto al fatto che l'utente non ha le autorizzazioni necessarie, problema che si può risolvere aggiungendo le autorizzazioni o usando i file in uno spazio di memorizzazione isolato.</span><span class="sxs-lookup"><span data-stu-id="2dfa7-108">This is often a result of the user lacking necessary permissions, which may be solved by adding permissions or working with files in isolated storage.</span></span>  
  
### <a name="file-encodings"></a><span data-ttu-id="2dfa7-109">Codifiche dei file</span><span class="sxs-lookup"><span data-stu-id="2dfa7-109">File encodings</span></span>  
 <span data-ttu-id="2dfa7-110">Le codifiche dei file, note anche come codifiche dei caratteri, specificano in che modo vengono rappresentati i caratteri durante l'elaborazione del testo.</span><span class="sxs-lookup"><span data-stu-id="2dfa7-110">File encodings, also known as character encodings, specify how to represent characters when text processing.</span></span> <span data-ttu-id="2dfa7-111">La presenza di caratteri non previsti in un file di testo può causare una codifica non corretta.</span><span class="sxs-lookup"><span data-stu-id="2dfa7-111">Unexpected characters in a text file may result from incorrect encoding.</span></span> <span data-ttu-id="2dfa7-112">Per la maggior parte dei file, una codifica può essere preferibile rispetto a un'altra per i caratteri del linguaggio che è o non è in grado di gestire, anche se in genere è preferibile Unicode.</span><span class="sxs-lookup"><span data-stu-id="2dfa7-112">For most files, one encoding may be preferable over another in terms of which language characters it can or cannot handle, although Unicode is usually preferred.</span></span> <span data-ttu-id="2dfa7-113">Per altre informazioni, vedere [Codifiche dei file](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) e <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="2dfa7-113">For more information, see [File Encodings](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) and <xref:System.Text.Encoding>.</span></span>  
  
### <a name="incorrect-paths"></a><span data-ttu-id="2dfa7-114">Percorsi non corretti</span><span class="sxs-lookup"><span data-stu-id="2dfa7-114">Incorrect paths</span></span>  
 <span data-ttu-id="2dfa7-115">Quando si analizzano i percorsi dei file, in particolare i percorsi relativi, è facile inserire i dati errati.</span><span class="sxs-lookup"><span data-stu-id="2dfa7-115">When parsing file paths, particularly relative paths, it is easy to supply the wrong data.</span></span> <span data-ttu-id="2dfa7-116">Molti problemi possono essere corretti verificando di avere specificato il percorso corretto.</span><span class="sxs-lookup"><span data-stu-id="2dfa7-116">Many problems can be corrected by making sure you are supplying the correct path.</span></span> <span data-ttu-id="2dfa7-117">Per altre informazioni, vedere [Procedura: Analizzare percorsi di file](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md).</span><span class="sxs-lookup"><span data-stu-id="2dfa7-117">For more information, see [How to: Parse File Paths](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dfa7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2dfa7-118">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- [<span data-ttu-id="2dfa7-119">Lettura da file</span><span class="sxs-lookup"><span data-stu-id="2dfa7-119">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="2dfa7-120">Scrittura su file</span><span class="sxs-lookup"><span data-stu-id="2dfa7-120">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [<span data-ttu-id="2dfa7-121">Analisi dei file di testo con l'oggetto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="2dfa7-121">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
