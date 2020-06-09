---
title: Delimitatori per i tag della documentazione-Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
ms.openlocfilehash: db8d43edc8b7cb0066fd3afcb75a1852603e86c4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594426"
---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a>Delimitatori per i tag della documentazione (Guida per programmatori C#)

L'uso dei commenti XML relativi alla documentazione richiede la specifica di delimitatori per indicare al compilatore il punto di inizio e di fine di un commento relativo alla documentazione. È possibile usare con i tag della documentazione XML i tipi di delimitatori seguenti:

- `///`

  Delimitatore di riga singola. Questo è il formato illustrato negli esempi di documentazione e usato dai modelli di progetto C#. Se dopo il delimitatore è presente un carattere di spazio vuoto, quest'ultimo non è incluso nell'output XML.

  > [!NOTE]
  > Il Integrated Development Environment (IDE) di Visual Studio inserisce automaticamente `<summary>` i `</summary>` tag e e sposta il cursore all'interno di questi tag dopo aver digitato il `///` delimitatore nell'editor di codice. È possibile attivare o disattivare questa funzionalità nella [finestra di dialogo Opzioni](/visualstudio/ide/reference/options-text-editor-csharp-advanced).
  
- `/** */`

  Delimitatori di più righe.

  Quando si usano i delimitatori, è necessario seguire alcune regole di formattazione `/** */` :
  
  - Nella riga contenente il delimitatore `/**` se la parte restante della riga è rappresentata da uno spazio vuoto, la riga non viene elaborata per i commenti. Se il primo carattere dopo il delimitatore `/**` è uno spazio vuoto, lo spazio vuoto viene ignorato e il resto della riga viene elaborato. In caso contrario, l'intero testo della riga dopo il delimitatore `/**` viene elaborato come parte del commento.

  - Se sulla riga contenente il delimitatore `*/` sono presenti solo spazi vuoti fino al delimitatore `*/`, la riga viene ignorata. In caso contrario, il testo nella riga fino al `*/` delimitatore viene elaborato come parte del commento.
  
  - Per le righe successive a quella che inizia con il delimitatore `/**`, il compilatore cerca un modello comune all'inizio di ogni riga. Il modello può essere costituito da uno spazio vuoto facoltativo e un asterisco (`*`) seguiti da altri spazi vuoti facoltativi. Se trova un modello comune all'inizio di ogni riga che non inizia con il delimitatore `/**` o `*/`, il compilatore ignora tale modello per ogni riga.

  Gli esempi seguenti illustrano queste regole.

  - L'unica parte del commento seguente elaborato è la riga che inizia con `<summary>` . I tre formati di tag producono gli stessi commenti.

    ```csharp
    /** <summary>text</summary> */

    /**
    <summary>text</summary>
    */

    /**
     * <summary>text</summary>
    */
    ```

  - Il compilatore identifica un modello comune di " \* " all'inizio della seconda e della terza riga. Il modello non è incluso nell'output.

    ```csharp
    /**
     * <summary>
     * text </summary>*/
    ```

  - Il compilatore non trova alcun modello comune nel commento seguente poiché il secondo carattere nella terza riga non è un asterisco. Di conseguenza, tutto il testo contenuto nella seconda e nella terza riga viene elaborato come parte del commento.

    ```csharp
    /**
     * <summary>
       text </summary>
    */
    ```

  - Nel commento seguente il compilatore non rileva alcun modello per due motivi. In primo luogo, il numero di spazi prima dell'asterisco non è coerente. In secondo luogo, la quinta riga inizia con una tabulazione senza corrispondenza degli spazi. Di conseguenza, tutto il testo dalla seconda alla quinta riga verrà elaborato come parte del commento.

    <!-- markdownlint-disable MD010 -->
    ```csharp
    /**
      * <summary>
      * text
     *  text2
        *  </summary>
    */
    ```
    <!-- markdownlint-enable MD010 -->

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Commenti relativi alla documentazione XML](./index.md)
- [-DOC (opzioni del compilatore C#)](../../language-reference/compiler-options/doc-compiler-option.md)
