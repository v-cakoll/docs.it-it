---
title: Codifiche dei file
ms.date: 07/20/2015
helpviewer_keywords:
- character encodings
- files [Visual Basic], encoding
- Unicode, file encoding
- file encoding
ms.assetid: ea2c5f5f-bbb1-4150-9928-b9951fa6bc57
ms.openlocfilehash: f906b2f2d747a7950c70a24549bbf5423e5b87b4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401745"
---
# <a name="file-encodings-visual-basic"></a><span data-ttu-id="a0cec-102">Codifiche dei file (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0cec-102">File Encodings (Visual Basic)</span></span>

<span data-ttu-id="a0cec-103">Le codifiche dei file, note anche come codifiche dei caratteri, specificano in che modo vengono rappresentati i caratteri durante l'elaborazione del testo.</span><span class="sxs-lookup"><span data-stu-id="a0cec-103">File encodings, also known as character encodings, specify how to represent characters when text processing.</span></span> <span data-ttu-id="a0cec-104">Una codifica può essere preferibile rispetto a un'altra per i caratteri del linguaggio che è o non è in grado di gestire, anche se in genere è preferibile Unicode.</span><span class="sxs-lookup"><span data-stu-id="a0cec-104">One encoding may be preferable over another in terms of which language characters it can or cannot handle, although Unicode is usually preferred.</span></span>

<span data-ttu-id="a0cec-105">Durante la lettura da o la scrittura su file, le codifiche dei file non corrispondenti possono generare eccezioni o risultati errati.</span><span class="sxs-lookup"><span data-stu-id="a0cec-105">When reading from or writing to files, improperly matching file encodings may result in exceptions or incorrect results.</span></span>

## <a name="types-of-encodings"></a><span data-ttu-id="a0cec-106">Tipi di codifiche</span><span class="sxs-lookup"><span data-stu-id="a0cec-106">Types of Encodings</span></span>

<span data-ttu-id="a0cec-107">Unicode è la codifica preferita quando si lavora con i file.</span><span class="sxs-lookup"><span data-stu-id="a0cec-107">Unicode is the preferred encoding when working with files.</span></span> <span data-ttu-id="a0cec-108">Unicode è uno standard di codifica dei caratteri a livello mondiale che usa valori di codice a 16 bit per rappresentare tutti i caratteri usati nei sistemi informatici moderni, compresi i simboli tecnici e caratteri speciali usati per la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="a0cec-108">Unicode is a worldwide character-encoding standard that uses 16-bit code values to represent all the characters used in modern computing, including technical symbols and special characters used in publishing.</span></span>

<span data-ttu-id="a0cec-109">Gli standard di codifica dei caratteri precedenti erano costituiti da set di caratteri tradizionali, ad esempio il set di caratteri ANSI di Windows che usa valori di codice a 8 bit, o combinazioni di valori a 8 bit, per rappresentare i caratteri usati in una lingua o un'area geografica specifica.</span><span class="sxs-lookup"><span data-stu-id="a0cec-109">Previous character-encoding standards consisted of traditional character sets, such as the Windows ANSI character set that uses 8-bit code values, or combinations of 8-bit values, to represent the characters used in a specific language or geographical region.</span></span>

## <a name="encoding-class"></a><span data-ttu-id="a0cec-110">Classe di codifica</span><span class="sxs-lookup"><span data-stu-id="a0cec-110">Encoding Class</span></span>

<span data-ttu-id="a0cec-111">La classe <xref:System.Text.Encoding> rappresenta una codifica dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="a0cec-111">The <xref:System.Text.Encoding> class represents a character encoding.</span></span> <span data-ttu-id="a0cec-112">In questa tabella sono elencati i tipi di codifica disponibili con una descrizione di ogni tipo.</span><span class="sxs-lookup"><span data-stu-id="a0cec-112">This table lists the type of encodings available and describes each.</span></span>

|<span data-ttu-id="a0cec-113">Nome</span><span class="sxs-lookup"><span data-stu-id="a0cec-113">Name</span></span>|<span data-ttu-id="a0cec-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0cec-114">Description</span></span>|
|---|---|
|<xref:System.Text.ASCIIEncoding>|<span data-ttu-id="a0cec-115">Rappresenta una codifica dei caratteri ASCII di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="a0cec-115">Represents an ASCII character encoding of Unicode characters.</span></span>|
|<xref:System.Text.UnicodeEncoding>|<span data-ttu-id="a0cec-116">Rappresenta una codifica UTF-16 dei caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="a0cec-116">Represents a UTF-16 encoding of Unicode characters.</span></span>|
|<xref:System.Text.UTF32Encoding>|<span data-ttu-id="a0cec-117">Rappresenta una codifica UTF-32 dei caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="a0cec-117">Represents a UTF-32 encoding of Unicode characters.</span></span>|
|<xref:System.Text.UTF7Encoding>|<span data-ttu-id="a0cec-118">Rappresenta una codifica UTF-7 dei caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="a0cec-118">Represents a UTF-7 encoding of Unicode characters.</span></span>|
|<xref:System.Text.UTF8Encoding>|<span data-ttu-id="a0cec-119">Rappresenta una codifica UTF-8 dei caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="a0cec-119">Represents a UTF-8 encoding of Unicode characters.</span></span>|

## <a name="see-also"></a><span data-ttu-id="a0cec-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0cec-120">See also</span></span>

- [<span data-ttu-id="a0cec-121">Lettura da file</span><span class="sxs-lookup"><span data-stu-id="a0cec-121">Reading from Files</span></span>](reading-from-files.md)
- [<span data-ttu-id="a0cec-122">Scrittura in file</span><span class="sxs-lookup"><span data-stu-id="a0cec-122">Writing to Files</span></span>](writing-to-files.md)
