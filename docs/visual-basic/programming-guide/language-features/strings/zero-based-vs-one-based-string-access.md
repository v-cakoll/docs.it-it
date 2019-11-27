---
title: Accesso con stringa in base zero e in base uno
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: 97e60038bc7ec0f030939d0980b786bffebcfb9a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354292"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Accesso alle stringhe in base zero o in base uno in Visual Basic
In questo argomento viene illustrato il modo in cui Visual Basic e il .NET Framework consentono di accedere ai caratteri in una stringa. Il .NET Framework fornisce sempre l'accesso in base zero ai caratteri in una stringa, mentre Visual Basic fornisce l'accesso in base zero e uno a seconda della funzione.  
  
## <a name="one-based"></a>In base uno  
 Per un esempio di una funzione Visual Basic basata su uno, prendere in considerazione la funzione `Mid`. Accetta un argomento che indica la posizione del carattere in corrispondenza della quale verrà avviata la sottostringa, a partire dalla posizione 1. Il .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> metodo accetta un indice del carattere nella stringa in corrispondenza del quale viene avviata la sottostringa, a partire dalla posizione 0. Pertanto, se si dispone di una stringa "ABCDe", i singoli caratteri sono numerati 1, 2, 3, 4, 5 per l'utilizzo con la funzione `Mid`, ma 0, 1, 2, 3, 4 per l'utilizzo con il metodo di <xref:System.String.Substring%2A?displayProperty=nameWithType>.  
  
## <a name="zero-based"></a>In base zero  
 Per un esempio di funzione Visual Basic in base zero, prendere in considerazione la funzione `Split`. Suddivide una stringa e restituisce una matrice contenente le sottostringhe. Il .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> metodo suddivide anche una stringa e restituisce una matrice contenente le sottostringhe. Poiché la funzione `Split` e il metodo <xref:System.String.Split%2A> restituiscono .NET Framework matrici, devono essere in base zero.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
