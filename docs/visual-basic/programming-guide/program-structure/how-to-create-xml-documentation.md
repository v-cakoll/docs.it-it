---
title: 'Procedura: creare documentazione XLM in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 7fb56da8a28367a6dcd5e28f208b4519510d7d95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Procedura: creare documentazione XLM in Visual Basic
In questo esempio viene illustrato come aggiungere commenti della documentazione XML al codice.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>Per creare la documentazione XML per un tipo o membro  
  
1.  Nel **Editor di codice**, posizionare il cursore sulla riga di sopra del tipo o membro per il quale si desidera creare la documentazione.  
  
2.  Tipo `'''` (tre virgolette singole).  
  
     Uno scheletro XML per il tipo o il membro viene aggiunto nel **Editor di codice**.  
  
3.  Aggiungere informazioni descrittive tra i tag appropriati.  
  
    > [!NOTE]
    >  Se si aggiungono le righe all'interno del blocco di documentazione XML, ogni riga deve iniziare con `'''`.  
  
4.  Aggiungere codice che utilizza il tipo o il membro con i nuovi commenti della documentazione XML.  
  
     IntelliSense consente di visualizzare il testo di \<riepilogo > tag per il tipo o membro.  
  
5.  Compilare il codice per generare un file XML contenente i commenti della documentazione. Per altre informazioni, vedere [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Documentazione del codice tramite XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
