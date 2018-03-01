---
title: Visual Studio in base zero. Accesso basato su una stringa in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 911f063d6ca9a3f5d88a1f50d9df7f908a488f66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Visual Studio in base zero. Accesso basato su una stringa in Visual Basic
Questo argomento vengono confrontate come [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] e [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] forniscono l'accesso ai caratteri in una stringa. Il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] fornisce sempre l'accesso in base zero per i caratteri in una stringa, mentre [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] fornisce l'accesso in base zero e in base uno, a seconda della funzione.  
  
## <a name="one-based"></a>In base uno  
 Per un esempio di base uno [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] di funzione, prendere in considerazione il `Mid` (funzione). Accetta un argomento che indica la posizione del carattere in corrispondenza del quale inizia la sottostringa, a partire dalla posizione 1. Il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> metodo accetta un indice del carattere nella stringa in corrispondenza del quale inizia la sottostringa per avviare, a partire dalla posizione 0. Pertanto, se si dispone di una stringa "ABCDE", i singoli caratteri sono numerati 1,2,3,4,5 per l'utilizzo con il `Mid` funzione, ma 0,1,2,3,4 per l'utilizzo con il <xref:System.String.Substring%2A?displayProperty=nameWithType> metodo.  
  
## <a name="zero-based"></a>In base zero  
 Per un esempio di oggetto in base zero [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] di funzione, prendere in considerazione il `Split` (funzione). Suddivide una stringa e restituisce una matrice contenente le sottostringhe. Il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> anche metodo suddivide una stringa e restituisce una matrice contenente le sottostringhe. Poiché il `Split` funzione e <xref:System.String.Split%2A> metodo [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] matrici, devono essere in base zero.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:System.String.Substring%2A>  
 <xref:System.String.Split%2A>  
 [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
