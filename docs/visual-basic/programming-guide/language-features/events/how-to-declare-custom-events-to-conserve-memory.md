---
title: 'Procedura: dichiarare eventi personalizzati per proteggere la memoria'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: 3cc2d3ea57f1a8daf704c2c929baf3f2acf78c17
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345136"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Procedura: dichiarare eventi personalizzati per proteggere la memoria (Visual Basic)
In alcuni casi è importante che un'applicazione mantenga l'utilizzo di memoria basso. Gli eventi personalizzati consentono all'applicazione di usare la memoria solo per gli eventi gestiti.  
  
 Per impostazione predefinita, quando una classe dichiara un evento, il compilatore alloca memoria per un campo per archiviare le informazioni sull'evento. Se una classe dispone di molti eventi non utilizzati, inutilmente si occupino di memoria.  
  
 Invece di usare l'implementazione predefinita di eventi forniti da Visual Basic, è possibile usare gli eventi personalizzati per gestire l'utilizzo della memoria con maggiore attenzione.  
  
## <a name="example"></a>Esempio  
 In questo esempio, la classe usa un'istanza della classe <xref:System.ComponentModel.EventHandlerList>, archiviata nel campo `Events`, per archiviare le informazioni sugli eventi in uso. La classe <xref:System.ComponentModel.EventHandlerList> è una classe di elenco ottimizzata progettata per ospitare delegati.  
  
 Tutti gli eventi nella classe usano il campo `Events` per tenere traccia dei metodi che gestiscono ogni evento.  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.EventHandlerList>
- [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Procedura: Dichiarare eventi personalizzati per evitare il blocco](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
