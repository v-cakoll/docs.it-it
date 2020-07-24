---
title: Creazione del documento Office Open XML di origine (C#)
description: Creare un documento WordprocessingML di Office Open XML da usare con le esercitazioni su C#. Questo articolo richiede Microsoft Office.
ms.date: 07/20/2015
ms.assetid: 653c8cdb-73be-4dc2-927f-924cfb4ed9ed
ms.openlocfilehash: e6d6908ee6560218793454f3871705e74095f543
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103999"
---
# <a name="creating-the-source-office-open-xml-document-c"></a>Creazione del documento Office Open XML di origine (C#)

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

    using System;

    class Program {
        public static void Main(string[] args) {
            Console.WriteLine("Hello World");
        }
    }

    This example produces the following output:

    Hello World
    ```

3. Formattare la prima riga con lo stile "Intestazione 1".

4. Selezionare le righe contenenti codice C#. La prima riga inizia con la parola chiave `using`. L'ultima riga corrisponde all'ultima parentesi graffa di chiusura. Formattare le righe con il tipo di carattere Courier. Formattarle con un nuovo stile, da denominare "Code".

5. Infine, selezionare l'intera riga che contiene l'output e formattarla con lo stile `Code`.

6. Salvare il documento e denominarlo SampleDoc.docx.

    > [!NOTE]
    > Se si usa Microsoft Word 2003, selezionare **Documento di Word 2007** nell'elenco a discesa **Tipo file**.
