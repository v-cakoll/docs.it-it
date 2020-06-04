---
title: Creazione del documento Office Open XML di origine
ms.date: 07/20/2015
ms.assetid: 61ccd6fb-0c47-4075-afdf-5b5021330f21
ms.openlocfilehash: 9f44c8d0f4080224c461736fdbdf3acd854e4a89
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410838"
---
# <a name="creating-the-source-office-open-xml-document-visual-basic"></a>Creazione del documento Office Open XML di origine (Visual Basic)
In questo argomento viene illustrato come creare il documento WordprocessingML di Office Open XML usato in altri esempi di questa esercitazione. Seguendo queste istruzioni, l'output ottenuto sarà uguale a quello indicato in ogni esempio.  
  
 Tuttavia, gli esempi presentati in questa esercitazione funzioneranno con qualsiasi documento WordprocessingML valido.  
  
 Per creare il documento usato in questa esercitazione, è necessario che nel computer sia installato Microsoft Office 2007 o versione successiva oppure Microsoft Office 2003 con il pacchetto di compatibilità per Microsoft Office per i formati di file Word, Excel e PowerPoint 2007.  
  
## <a name="creating-the-wordprocessingml-document"></a>Creazione del documento WordprocessingML  
  
#### <a name="to-create-the-wordprocessingml-document"></a>Per creare il documento WordprocessingML  
  
1. Creare un nuovo documento di Microsoft Word.  
  
2. Incollare il testo seguente nel nuovo documento:  
  
    ```text  
    Parsing WordprocessingML with LINQ to XML  
  
    The following example prints to the console.  
  
    Imports System  
  
    Class Program  
        Public Shared  Sub Main(ByVal args() As String)  
            Console.WriteLine("Hello World")  
        End Sub  
    End Class  
  
    This example produces the following output:  
  
    Hello World  
    ```  
  
3. Formattare la prima riga con lo stile "Intestazione 1".  
  
4. Selezionare le righe che contengono il codice Visual Basic. La prima riga inizia con la parola chiave `Imports`. L'ultima riga è "End Class". Formattare le righe con il tipo di carattere Courier. Formattarle con un nuovo stile, da denominare "Code".  
  
5. Infine, selezionare l'intera riga che contiene l'output e formattarla con lo stile `Code`.  
  
6. Salvare il documento e denominarlo SampleDoc.docx.  
  
    > [!NOTE]
    > Se si usa Microsoft Word 2003, selezionare **Documento di Word 2007** nell'elenco a discesa **Tipo file**.  
  
## <a name="see-also"></a>Vedere anche

- [Esercitazione: modifica del contenuto in un documento WordprocessingML (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md)
