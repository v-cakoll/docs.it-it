---
title: Creazione del documento Office Open XML di origine (C#)
ms.date: 07/20/2015
ms.assetid: 653c8cdb-73be-4dc2-927f-924cfb4ed9ed
ms.openlocfilehash: d6c4d8866bba58e86735099a62041894a9faa9b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70204162"
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
