---
title: Tipi di dati vari (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6bb86bb6d203aa4e6bdded27a4cb78a8155ddec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="miscellaneous-data-types-visual-basic"></a>Tipi di dati vari (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]fornisce diversi tipi di dati che non sono orientati verso i numeri o caratteri. In alternativa, occuparsi di dati speciali, ad esempio Sì/no valori, valori data/ora e oggetto indirizzi.  
  
 Per una tabella che mostra un confronto side-by-side del [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] tipi di dati, vedere [tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="boolean-type"></a>Tipo booleano  
 Il [tipo di dati Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) è un valore senza segno viene interpretato come `True` o `False`. La larghezza dei dati dipende dalla piattaforma di implementazione. Se una variabile può contenere solo valori di due stati, ad esempio true/false, sì/no o on/off, dichiararla come `Boolean`.  
  
## <a name="date-type"></a>Date (tipo)  
 Il [tipo di dati Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) è un valore a 64 bit che contiene le informazioni sia data e ora. Ogni incremento rappresenta 100 nanosecondi di tempo trascorso dall'inizio (12:00 AM) del 1 ° gennaio dell'anno 1 del calendario gregoriano. Se una variabile può contenere un valore di data, un valore di ora o entrambi, dichiararla come `Date`.  
  
## <a name="object-type"></a>Tipo di oggetto  
 Il [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) è un indirizzo a 32 bit che punta a un'istanza dell'oggetto all'interno dell'applicazione o in un'altra applicazione. Un `Object` variabile può fare riferimento a qualsiasi oggetto riconosciuto dall'applicazione o ai dati di qualsiasi tipo di dati. Sono inclusi sia *i tipi di valore*, ad esempio `Integer`, `Boolean`e le istanze della struttura, e *tipi di riferimento*, che sono istanze di oggetti creati da classi, ad esempio `String`e <xref:System.Windows.Forms.Form>e matrice di istanze.  
  
 Se una variabile archivia un puntatore a un'istanza di una classe che non si conosce in fase di compilazione o se può puntare a vari tipi di dati, dichiararlo come `Object`.  
  
 Il vantaggio del `Object` è di tipo di dati che è possibile utilizzare per archiviare i dati di qualsiasi tipo di dati. Lo svantaggio è che sono necessarie ulteriori operazioni che richiedono più tempo di esecuzione e rendere l'applicazione di esecuzione più lenta. Se si utilizza un `Object` variabili per i tipi di valore, si devono sostenere *boxing* e *unboxing*. Se si utilizza per i tipi di riferimento, sono necessarie *ad associazione tardiva*.  
  
## <a name="see-also"></a>Vedere anche  
 [Caratteri tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Tipi di dati numerici](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [Dati di tipo carattere](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Associazione anticipata e tardiva](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
