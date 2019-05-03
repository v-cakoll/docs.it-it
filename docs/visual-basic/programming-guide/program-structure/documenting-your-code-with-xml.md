---
title: Documentazione del codice tramite XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: 6b9fe9994b7bdf2259dcdb1ecef906e0f9955c8f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785502"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a>Documentazione del codice tramite XML (Visual Basic)

In Visual Basic, è possibile documentare il codice tramite XML

## <a name="xml-documentation-comments"></a>Commenti relativi alla documentazione XML

Visual Basic fornisce un modo semplice per creare automaticamente la documentazione XML per i progetti. È possibile generare automaticamente una struttura XML per i tipi e membri e quindi fornire i riepiloghi, documentazione descrittiva per ogni parametro e altre note. Con la configurazione appropriata, la documentazione XML viene generata automaticamente in un file XML con lo stesso nome del progetto e l'estensione. Xml. Per altre informazioni, vedere [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).

Il file XML può essere utilizzato o altrimenti modificato come XML. Questo file si trova nella stessa directory del file .exe o DLL di output del progetto.

Documentazione XML inizia con `'''`. L'elaborazione di questi commenti presenta alcune restrizioni:

- La documentazione deve essere in codice XML ben formato. Se il codice XML non è corretto, viene generato un avviso e il file di documentazione contiene un commento per informare che si è verificato un errore.

- Gli sviluppatori sono liberi di creare set di tag personalizzati. È presente un set di tag (vedere "Sezioni correlate" in questo argomento). Alcuni tag consigliati hanno un significato speciale:

  - Il tag \< viene usato per descrivere i parametri. Se usato, il compilatore verifica che il parametro esista e che tutti i parametri siano descritti nella documentazione. Se la verifica ha esito negativo, il compilatore genera un avviso.

  - L'attributo `cref` può essere associato a qualsiasi tag per fornire un riferimento a un elemento del codice. Il compilatore verifica l'esistenza di questo elemento. Se la verifica ha esito negativo, il compilatore genera un avviso. Il compilatore rispetta anche eventuali `Imports` istruzioni durante la ricerca di un tipo descritto nel `cref` attributo.

  - Il \<riepilogo > tag viene usato da IntelliSense in Visual Studio per visualizzare informazioni aggiuntive su un tipo o membro.

## <a name="related-sections"></a>Sezioni correlate

Per informazioni dettagliate sulla creazione di un file XML con i commenti della documentazione, vedere gli argomenti seguenti:

- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)

- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)

- [Elaborazione del file XML](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [Procedura: Creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [Strumenti XML in Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a>Vedere anche

- [Sviluppo di applicazioni con Visual Basic](../../../visual-basic/developing-apps/index.md)
- [Guida per programmatori Visual Basic](../../../visual-basic/programming-guide/index.md)
