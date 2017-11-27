---
title: Comportamento di Nothing con le stringhe in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ce9f81f23f50e38f6b1ad5e638e8c6ac026e992
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="nothing-and-strings-in-visual-basic"></a>Comportamento di Nothing con le stringhe in Visual Basic
Il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] runtime e [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] valutare `Nothing` in modo diverso quando si lavora con stringhe.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Runtime di Visual Basic e .NET Framework  
 Si consideri l'esempio seguente:  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 Il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] runtime restituisce in genere `Nothing` come una stringa vuota (""). Il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] non, tuttavia e genera un'eccezione ogni volta che viene effettuato un tentativo di eseguire un'operazione di stringa su `Nothing`.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
