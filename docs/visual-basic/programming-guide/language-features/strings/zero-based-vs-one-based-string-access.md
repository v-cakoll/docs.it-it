---
title: Accesso alle stringhe in base zero Accesso basato su una stringa in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: a6ceb10d4a3cb9463551d8c85375ddbbb607ffdc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830331"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Accesso alle stringhe in base zero Accesso basato su una stringa in Visual Basic
Questo argomento vengono confrontati come Visual Basic e [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] forniscono l'accesso ai caratteri in una stringa. Il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] fornisce sempre l'accesso in base zero per i caratteri in una stringa, mentre Visual Basic fornisce l'accesso in base zero e in base uno, a seconda della funzione.  
  
## <a name="one-based"></a>In base uno  
 Per un esempio di una funzione di Visual Basic in base uno, prendere in considerazione il `Mid` (funzione). Accetta un argomento che indica la posizione del carattere in corrispondenza del quale inizia la sottostringa, a partire dalla posizione 1. Il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> metodo accetta un indice del carattere nella stringa in corrispondenza del quale la sottostringa consiste nell'iniziare, a partire dalla posizione 0. Di conseguenza, se si dispone di una stringa "ABCDE", singoli caratteri sono numerati 1,2,3,4,5 per l'uso con il `Mid` funzione, ma 0,1,2,3,4 per l'uso con il <xref:System.String.Substring%2A?displayProperty=nameWithType> (metodo).  
  
## <a name="zero-based"></a>In base zero  
 Per un esempio di una funzione di Visual Basic in base zero, prendere in considerazione il `Split` (funzione). Suddivide una stringa e restituisce una matrice contenente le sottostringhe. Il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> metodo inoltre suddivide una stringa e restituisce una matrice contenente le sottostringhe. Poiché il `Split` (funzione) e <xref:System.String.Split%2A> metodo restituiscono [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] matrici, devono essere in base zero.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
