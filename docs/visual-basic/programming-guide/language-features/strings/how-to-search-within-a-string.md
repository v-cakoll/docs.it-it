---
title: "Procedura: eseguire la ricerca all'interno di una stringa-Visual Basic"
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: fe9e50dc5458fdf8546094e5f41c2f001f1d2791
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700069"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="e7675-102">Procedura: eseguire la ricerca all'interno di una stringa (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7675-102">How to: search within a string (Visual Basic)</span></span>

<span data-ttu-id="e7675-103">Questo articolo illustra un esempio di come eseguire una ricerca all'interno di una stringa in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e7675-103">This article shows an example of how to search within a string in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="e7675-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7675-104">Example</span></span>

<span data-ttu-id="e7675-105">In questo esempio viene chiamato il metodo <xref:System.String.IndexOf%2A> su un oggetto <xref:System.String> per segnalare l'indice della prima occorrenza di una sottostringa:</span><span class="sxs-lookup"><span data-stu-id="e7675-105">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring:</span></span>

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a><span data-ttu-id="e7675-106">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="e7675-106">Robust programming</span></span>

<span data-ttu-id="e7675-107">Il metodo <xref:System.String.IndexOf%2A> restituisce la posizione del primo carattere della prima occorrenza della sottostringa.</span><span class="sxs-lookup"><span data-stu-id="e7675-107">The <xref:System.String.IndexOf%2A> method returns the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="e7675-108">L'indice è in base 0, il che significa che il primo carattere di una stringa ha un indice pari a 0.</span><span class="sxs-lookup"><span data-stu-id="e7675-108">The index is 0-based, which means the first character of a string has an index of 0.</span></span>

<span data-ttu-id="e7675-109">Se <xref:System.String.IndexOf%2A> non trova la sottostringa, viene restituito-1.</span><span class="sxs-lookup"><span data-stu-id="e7675-109">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>

<span data-ttu-id="e7675-110">Il metodo <xref:System.String.IndexOf%2A> fa distinzione tra maiuscole e minuscole e usa le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="e7675-110">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>

<span data-ttu-id="e7675-111">Per un controllo degli errori ottimale, potrebbe essere necessario racchiudere la ricerca della stringa nel blocco `Try` di un [try... Rileva... Costruzione di istruzioni finally](../../../language-reference/statements/try-catch-finally-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="e7675-111">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md) construction.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7675-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7675-112">See also</span></span>

- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="e7675-113">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="e7675-113">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="e7675-114">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7675-114">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
- [<span data-ttu-id="e7675-115">Stringhe</span><span class="sxs-lookup"><span data-stu-id="e7675-115">Strings</span></span>](index.md)
