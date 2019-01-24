---
title: Tipi di dati vari (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: 7e32bf158b91c23c32028eb6877bd0089a9019b2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655049"
---
# <a name="miscellaneous-data-types-visual-basic"></a>Tipi di dati vari (Visual Basic)
Visual Basic offre diversi tipi di dati che non sono orientati verso i numeri o caratteri. Al contrario, gestiscono dati specializzati, ad esempio Sì/no valori, valori data/ora e oggetto indirizzi.  
  
 Per una tabella che mostra un confronto side-by-side dei tipi di dati Visual Basic, vedere [tipi di dati](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="boolean-type"></a>Tipo booleano  
 Il [tipo di dati Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) è un valore senza segno che viene interpretato come una `True` o `False`. La larghezza dei dati dipende dalla piattaforma di implementazione. Se una variabile può contenere solo i valori di due stati, ad esempio true/false, sì/no o on/off, dichiararla come `Boolean`.  
  
## <a name="date-type"></a>Tipo date  
 Il [tipo di dati Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) è un valore a 64 bit che contiene le informazioni relative sia data e ora. Ogni incremento rappresenta 100 nanosecondi di tempo trascorso dall'inizio (12:00 AM) del 1 ° gennaio dell'anno 1 del calendario gregoriano. Se una variabile può contenere un valore di data, un valore di ora o entrambe, dichiararla come `Date`.  
  
## <a name="object-type"></a>Tipo di oggetto  
 Il [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) è un indirizzo di 32 bit che punta a un'istanza dell'oggetto all'interno dell'applicazione o in un'altra applicazione. Un `Object` variabile può fare riferimento ad alcun oggetto riconosciuto dall'applicazione o ai dati di qualsiasi tipo di dati. Sono inclusi i *i tipi di valore*, ad esempio `Integer`, `Boolean`e istanze della struttura, e *fanno riferimento ai tipi*, che sono istanze degli oggetti creati dalle classi, ad esempio `String`e <xref:System.Windows.Forms.Form>e le istanze di matrice.  
  
 Se una variabile archivia un puntatore a un'istanza di una classe che non si conosce in fase di compilazione oppure può puntare a dati di vari tipi di dati, dichiararla come `Object`.  
  
 Il vantaggio del `Object` è di tipo di dati che è possibile usare per archiviare i dati di qualsiasi tipo di dati. Lo svantaggio è che sono necessarie operazioni aggiuntive che richiedono più tempo di esecuzione e rendere l'applicazione calo delle prestazioni. Se si usa un' `Object` variabili per i tipi valore, si incorre *boxing* e *unboxing*. Se è utilizzata per i tipi di riferimento, comportano *associazione tardiva*.  
  
## <a name="see-also"></a>Vedere anche
- [Caratteri tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipi di dati numerici](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [Dati di tipo carattere](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Associazione anticipata e tardiva](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
