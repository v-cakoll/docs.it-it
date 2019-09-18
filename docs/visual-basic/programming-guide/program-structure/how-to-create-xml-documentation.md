---
title: 'Procedura: Creazione di documentazione XML in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: ff93a7bb2d8fdef68fc956d4c569ca5ad37afb2c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054106"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Procedura: Creazione di documentazione XML in Visual Basic

Questo esempio illustra come aggiungere commenti alla documentazione XML al codice.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-xml-documentation-for-a-type-or-member"></a>Per creare la documentazione XML per un tipo o un membro

1. Nell' **editor di codice**posizionare il cursore sulla riga al di sopra del tipo o del membro per il quale si desidera creare la documentazione.

2. Digitare `'''` (tre virgolette singole).

    Un'ossatura XML per il tipo o il membro viene aggiunta nell' **editor di codice**.

3. Aggiungere informazioni descrittive tra i tag appropriati.

    > [!NOTE]
    > Se si aggiungono righe aggiuntive all'interno del blocco di documentazione XML, ogni riga `'''`deve iniziare con.

4. Aggiungere codice aggiuntivo che utilizza il tipo o il membro con i nuovi commenti della documentazione XML.

    IntelliSense consente di visualizzare il testo \<del Tag > di riepilogo per il tipo o il membro.

5. Compilare il codice per generare un file XML contenente i commenti della documentazione. Per altre informazioni, vedere [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).

## <a name="see-also"></a>Vedere anche

- [Documentazione del codice tramite XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
