---
title: Comportamento di Nothing con le stringhe in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d7693e712884a500495e4573900e7d9a049c2879
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="nothing-and-strings-in-visual-basic"></a>Comportamento di Nothing con le stringhe in Visual Basic
Runtime di Visual Basic e il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] valutare `Nothing` in modo diverso quando si tratta di stringhe.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Runtime di Visual Basic e .NET Framework  
 Si consideri l'esempio seguente:  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 Runtime di Visual Basic in genere valuta `Nothing` come una stringa vuota (""). Il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] non, tuttavia e genera un'eccezione ogni volta che viene effettuato un tentativo di eseguire un'operazione di stringa su `Nothing`.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
