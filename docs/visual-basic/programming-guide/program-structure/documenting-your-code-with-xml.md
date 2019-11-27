---
title: Documentazione del codice tramite XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: bdf0da7a8acc919e4a1d66b81e30c9ed912dd321
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347446"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a>Documentazione del codice tramite XML (Visual Basic)

In Visual Basic è possibile documentare il codice usando XML

## <a name="xml-documentation-comments"></a>Commenti relativi alla documentazione XML

Visual Basic fornisce un modo semplice per creare automaticamente la documentazione XML per i progetti. È possibile generare automaticamente uno scheletro XML per i tipi e i membri, quindi fornire riepiloghi, documentazione descrittiva per ogni parametro e altre osservazioni. Con la configurazione appropriata, la documentazione XML viene emessa automaticamente in un file XML con lo stesso nome del progetto e dell'estensione XML. Per altre informazioni, vedere [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).

Il file XML può essere utilizzato o modificato in altro modo come XML. Questo file si trova nella stessa directory del file con estensione exe o dll di output del progetto.

La documentazione XML inizia con `'''`. L'elaborazione di questi commenti presenta alcune restrizioni:

- La documentazione deve essere in codice XML ben formato. Se il formato XML non è corretto, viene generato un avviso e il file di documentazione contiene un commento che informa che si è verificato un errore.

- Gli sviluppatori sono liberi di creare set di tag personalizzati. È disponibile un set di tag consigliato (vedere "sezioni correlate" in questo argomento). Alcuni tag consigliati hanno un significato speciale:

  - Il tag \< viene usato per descrivere i parametri. Se usato, il compilatore verifica che il parametro esista e che tutti i parametri siano descritti nella documentazione. Se la verifica ha esito negativo, il compilatore genera un avviso.

  - L'attributo `cref` può essere associato a qualsiasi tag per fornire un riferimento a un elemento del codice. Il compilatore verifica l'esistenza di questo elemento. Se la verifica ha esito negativo, il compilatore genera un avviso. Il compilatore rispetta anche le istruzioni `Imports` quando si cerca un tipo descritto nell'attributo `cref`.

  - Il tag di riepilogo > \<viene usato da IntelliSense in Visual Studio per visualizzare informazioni aggiuntive su un tipo o un membro.

## <a name="related-sections"></a>Sezioni correlate

Per informazioni dettagliate sulla creazione di un file XML con i commenti relativi alla documentazione, vedere gli argomenti seguenti:

- [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)

- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)

- [Elaborazione del file XML](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [Procedura: Creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [Strumenti XML in Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a>Vedere anche

- [Sviluppo di applicazioni con Visual Basic](../../../visual-basic/developing-apps/index.md)
- [Guida per programmatori Visual Basic](../../../visual-basic/programming-guide/index.md)
