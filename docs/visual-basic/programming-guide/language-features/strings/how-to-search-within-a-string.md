---
title: "Procedura: eseguire la ricerca all'interno di una stringa"
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 655f746e4e496e1935afcd2a9f9fe36d9e3a2564
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348415"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="f4bb8-102">Procedura: eseguire la ricerca all'interno di una stringa (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4bb8-102">How to: search within a string (Visual Basic)</span></span>

<span data-ttu-id="f4bb8-103">Questo articolo illustra un esempio di come eseguire una ricerca all'interno di una stringa in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f4bb8-103">This article shows an example of how to search within a string in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="f4bb8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f4bb8-104">Example</span></span>

<span data-ttu-id="f4bb8-105">In questo esempio viene chiamato il metodo <xref:System.String.IndexOf%2A> su un oggetto <xref:System.String> per segnalare l'indice della prima occorrenza di una sottostringa:</span><span class="sxs-lookup"><span data-stu-id="f4bb8-105">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring:</span></span>

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a><span data-ttu-id="f4bb8-106">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="f4bb8-106">Robust programming</span></span>

<span data-ttu-id="f4bb8-107">Il metodo <xref:System.String.IndexOf%2A> restituisce la posizione del primo carattere della prima occorrenza della sottostringa.</span><span class="sxs-lookup"><span data-stu-id="f4bb8-107">The <xref:System.String.IndexOf%2A> method returns the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="f4bb8-108">L'indice è in base 0, il che significa che il primo carattere di una stringa ha un indice pari a 0.</span><span class="sxs-lookup"><span data-stu-id="f4bb8-108">The index is 0-based, which means the first character of a string has an index of 0.</span></span>

<span data-ttu-id="f4bb8-109">Se <xref:System.String.IndexOf%2A> non trova la sottostringa, viene restituito-1.</span><span class="sxs-lookup"><span data-stu-id="f4bb8-109">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>

<span data-ttu-id="f4bb8-110">Il metodo <xref:System.String.IndexOf%2A> distingue tra maiuscole e minuscole e usa le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="f4bb8-110">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>

<span data-ttu-id="f4bb8-111">Per un controllo degli errori ottimale, potrebbe essere necessario racchiudere la ricerca della stringa nel blocco `Try` di un'operazione [try... Rileva... Costruzione di istruzioni finally](../../../language-reference/statements/try-catch-finally-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="f4bb8-111">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md) construction.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4bb8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4bb8-112">See also</span></span>

- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="f4bb8-113">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="f4bb8-113">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="f4bb8-114">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f4bb8-114">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
- [<span data-ttu-id="f4bb8-115">Stringhe</span><span class="sxs-lookup"><span data-stu-id="f4bb8-115">Strings</span></span>](index.md)
