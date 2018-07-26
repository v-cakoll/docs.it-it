---
title: 'Procedura: creare documentazione XLM in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 7fb56da8a28367a6dcd5e28f208b4519510d7d95
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39243879"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Procedura: creare documentazione XLM in Visual Basic
In questo esempio viene illustrato come aggiungere commenti in formato documentazione XML nel codice.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>Per creare documentazione XML per un tipo o membro  
  
1.  Nel **Editor di codice**, posizionare il cursore sulla riga sopra il tipo o membro per cui si desidera creare la documentazione.  
  
2.  Tipo `'''` (tre virgolette singole).  
  
     Viene aggiunto uno scheletro XML per il tipo o membro di **Editor di codice**.  
  
3.  Aggiungere informazioni descrittive tra i tag appropriati.  
  
    > [!NOTE]
    >  Se si aggiungono altre righe all'interno del blocco di documentazione XML, ogni riga deve iniziare con `'''`.  
  
4.  Aggiungere altro codice che usa il tipo o membro con i nuovi commenti della documentazione XML.  
  
     IntelliSense visualizza il testo dal \<riepilogo > tag per il tipo o membro.  
  
5.  Compilare il codice per generare un file XML contenente i commenti della documentazione. Per altre informazioni, vedere [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Documentazione del codice tramite XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
