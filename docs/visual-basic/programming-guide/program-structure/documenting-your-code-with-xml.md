---
title: Documentazione del codice tramite XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: f391fb909cfe4de8f27afb24d6db389e2c8cdfae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590929"
---
# <a name="document-your-code-with-xml-visual-basic"></a>Documentare il codice con XML (Visual Basic)

In Visual Basic è possibile documentare il codice utilizzando XML.

## <a name="xml-documentation-comments"></a>Commenti relativi alla documentazione XML

Visual Basic fornisce un modo semplice per creare automaticamente la documentazione XML per i progetti. È possibile generare automaticamente uno scheletro XML per i tipi e i membri, quindi fornire riepiloghi, documentazione descrittiva per ogni parametro e altre osservazioni. Con la configurazione appropriata, la documentazione XML viene emessa automaticamente in un file XML con lo stesso nome file radice del progetto. Per ulteriori informazioni, vedere [-doc](../../reference/command-line-compiler/doc.md).

Il file XML può essere utilizzato o modificato in altro modo come XML. Questo file si trova nella stessa directory del file con estensione exe o dll di output del progetto.

La documentazione XML inizia con `'''` . L'elaborazione di questi commenti presenta alcune restrizioni:

- La documentazione deve essere in codice XML ben formato. Se il formato XML non è corretto, viene generato un avviso e il file di documentazione contiene un commento che informa che si è verificato un errore.

- Gli sviluppatori sono liberi di creare set di tag personalizzati. È disponibile un set di tag consigliato. vedere [tag di commento XML](../../language-reference/xmldoc/index.md). Alcuni tag consigliati hanno un significato speciale:

  - Il \<param> tag viene usato per descrivere i parametri. Se usato, il compilatore verifica che il parametro esista e che tutti i parametri siano descritti nella documentazione. Se la verifica ha esito negativo, il compilatore genera un avviso.

  - L'attributo `cref` può essere associato a qualsiasi tag per fornire un riferimento a un elemento del codice. Il compilatore verifica l'esistenza di questo elemento. Se la verifica ha esito negativo, il compilatore genera un avviso. Il compilatore rispetta anche le `Imports` istruzioni quando si cerca un tipo descritto nell' `cref` attributo.

  - Il \<summary> tag viene usato da IntelliSense in Visual Studio per visualizzare informazioni aggiuntive su un tipo o un membro.

## <a name="related-sections"></a>Sezioni correlate

Per informazioni dettagliate sulla creazione di un file XML con i commenti relativi alla documentazione, vedere gli argomenti seguenti:

- [-doc](../../reference/command-line-compiler/doc.md)

- [Tag di commento XML](../../language-reference/xmldoc/index.md)

- [Elaborazione del file XML](processing-the-xml-file.md)

- [Procedura: Creare documentazione XML](how-to-create-xml-documentation.md)

- [Strumenti XML in Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a>Vedere anche

- [Sviluppo di applicazioni con Visual Basic](../../developing-apps/index.md)
- [Guida per programmatori Visual Basic](../index.md)
