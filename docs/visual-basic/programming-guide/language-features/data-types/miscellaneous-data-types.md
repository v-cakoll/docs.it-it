---
title: Tipi di dati vari
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: cc6262b5bb305bb839917e222d831fa3340a1b14
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346341"
---
# <a name="miscellaneous-data-types-visual-basic"></a>Tipi di dati vari (Visual Basic)
Visual Basic fornisce diversi tipi di dati che non sono orientati verso numeri o caratteri. Si occupano invece di dati specializzati quali i valori Yes/No, i valori di data e ora e gli indirizzi degli oggetti.  
  
 Per una tabella che mostra un confronto affiancato dei tipi di dati Visual Basic, vedere tipi di [dati](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="boolean-type"></a>Tipo Boolean  
 Il [tipo di dati booleano](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) è un valore senza segno interpretato come `True` o `False`. La larghezza dei dati dipende dalla piattaforma di implementazione. Se una variabile può contenere solo valori a due Stati, ad esempio true/false, Yes/No o on/off, dichiararla come `Boolean`.  
  
## <a name="date-type"></a>Tipo di data  
 Il [tipo di dati date](../../../../visual-basic/language-reference/data-types/date-data-type.md) è un valore a 64 bit che include le informazioni di data e ora. Ogni incremento rappresenta 100 nanosecondi di tempo trascorso dall'inizio (12:00 AM) del 1 ° gennaio dell'anno 1 nel calendario gregoriano. Se una variabile può contenere un valore di data, un valore di ora o entrambi, dichiararla come `Date`.  
  
## <a name="object-type"></a>Tipo di oggetto  
 Il [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) è un indirizzo a 32 bit che punta a un'istanza dell'oggetto all'interno dell'applicazione o in un'altra applicazione. Una variabile di `Object` può fare riferimento a qualsiasi oggetto riconosciuto dall'applicazione o ai dati di qualsiasi tipo di dati. Sono inclusi entrambi i *tipi di valore*, ad esempio `Integer`, `Boolean`e le istanze di struttura e i tipi di *riferimento*, ovvero istanze di oggetti creati da classi quali `String` e <xref:System.Windows.Forms.Form>e istanze di matrice.  
  
 Se una variabile archivia un puntatore a un'istanza di una classe che non è noto in fase di compilazione o se può puntare a dati di vari tipi di dati, dichiararla come `Object`.  
  
 Il vantaggio del tipo di dati `Object` è che è possibile utilizzarlo per archiviare dati di qualsiasi tipo di dati. Lo svantaggio è che vengono eseguite operazioni aggiuntive che impongono un tempo di esecuzione maggiore e rallentano le prestazioni dell'applicazione. Se si usa una variabile di `Object` per i tipi di valore, si comporterà la *conversione boxing* e *unboxing.* Se viene usato per i tipi di riferimento, si incorre in un *binding tardivo*.  
  
## <a name="see-also"></a>Vedere anche

- [Caratteri tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipi di dati numerici](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [Dati di tipo carattere](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Associazione anticipata e tardiva](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
