---
title: Delimitatori per i tag della documentazione - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
ms.openlocfilehash: 064519e6d849736690f28c78e0efbc4067f9e6a9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711792"
---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a>Delimitatori per i tag della documentazione (Guida per programmatori C#)
L'uso dei commenti XML relativi alla documentazione richiede la specifica di delimitatori per indicare al compilatore il punto di inizio e di fine di un commento relativo alla documentazione. È possibile usare con i tag della documentazione XML i tipi di delimitatori seguenti:  
  
 `///`  
 Delimitatore di riga singola. Si tratta del formato riportato negli esempi della documentazione e usato per i modelli dei progetti Visual C#. Se dopo il delimitatore è presente un carattere di spazio vuoto, quest'ultimo non è incluso nell'output XML.  
  
> [!NOTE]
> Nell'IDE di Visual Studio è inclusa una funzionalità chiamata Smart Comment Editing (Modifica intelligente dei commenti) che consente di inserire automaticamente i tag \<summary> e \</summary> e di spostare il cursore all'interno di questi tag dopo aver digitato il delimitatore `///` nell'editor di codice. È possibile attivare o disattivare questa funzionalità nella [finestra di dialogo Opzioni](/visualstudio/ide/reference/options-text-editor-csharp-advanced).  
  
 `/** */`  
 Delimitatori di più righe.  
  
 Quando si usano i delimitatori `/** */` è necessario rispettare determinate regole di formattazione.  
  
- Nella riga contenente il delimitatore `/**` se la parte restante della riga è rappresentata da uno spazio vuoto, la riga non viene elaborata per i commenti. Se il primo carattere dopo il delimitatore `/**` è uno spazio vuoto, lo spazio vuoto viene ignorato e il resto della riga viene elaborato. In caso contrario, l'intero testo della riga dopo il delimitatore `/**` viene elaborato come parte del commento.  
  
- Se sulla riga contenente il delimitatore `*/` sono presenti solo spazi vuoti fino al delimitatore `*/`, la riga viene ignorata. In caso contrario, il testo contenuto nella riga fino al delimitatore `*/` viene elaborato come parte del commento, in base alle regole dei criteri di ricerca descritte nel punto che segue.  
  
- Per le righe successive a quella che inizia con il delimitatore `/**`, il compilatore cerca un modello comune all'inizio di ogni riga. Il modello può essere costituito da uno spazio vuoto facoltativo e un asterisco (`*`) seguiti da altri spazi vuoti facoltativi. Se trova un modello comune all'inizio di ogni riga che non inizia con il delimitatore `/**` o `*/`, il compilatore ignora tale modello per ogni riga.  
  
 Gli esempi seguenti illustrano queste regole.  
  
- La sola parte del commento riportato di seguito che verrà elaborata è la riga che inizia con `<summary>`. I tre formati di tag producono gli stessi commenti.  
  
    ```csharp  
    /** <summary>text</summary> */   
  
    /**   
    <summary>text</summary>   
    */   
  
    /**   
     * <summary>text</summary>   
    */  
    ```  
  
- Il compilatore identifica il modello comune " * " all'inizio della seconda e della terza riga. Il modello non è incluso nell'output.  
  
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
  
    ```csharp  
    /**   
      * <summary>   
      * text   
     *  text2   
        *  </summary>   
    */   
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Commenti relativi alla documentazione XML](./index.md)
- [-doc (opzioni del compilatore C#)](../../language-reference/compiler-options/doc-compiler-option.md)
- [Commenti relativi alla documentazione XML](./index.md)
