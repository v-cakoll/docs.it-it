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
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a><span data-ttu-id="17d06-102">Delimitatori per i tag della documentazione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="17d06-102">Delimiters for documentation tags (C# programming guide)</span></span>

<span data-ttu-id="17d06-103">L'uso dei commenti XML relativi alla documentazione richiede la specifica di delimitatori per indicare al compilatore il punto di inizio e di fine di un commento relativo alla documentazione.</span><span class="sxs-lookup"><span data-stu-id="17d06-103">The use of XML doc comments requires delimiters, which indicate to the compiler where a documentation comment begins and ends.</span></span> <span data-ttu-id="17d06-104">È possibile usare con i tag della documentazione XML i tipi di delimitatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="17d06-104">You can use the following kinds of delimiters with the XML documentation tags:</span></span>

- `///`

  <span data-ttu-id="17d06-105">Delimitatore di riga singola.</span><span class="sxs-lookup"><span data-stu-id="17d06-105">Single-line delimiter.</span></span> <span data-ttu-id="17d06-106">Questo è il formato illustrato negli esempi di documentazione e usato dai modelli di progetto C#.</span><span class="sxs-lookup"><span data-stu-id="17d06-106">This is the form that is shown in documentation examples and used by the C# project templates.</span></span> <span data-ttu-id="17d06-107">Se dopo il delimitatore è presente un carattere di spazio vuoto, quest'ultimo non è incluso nell'output XML.</span><span class="sxs-lookup"><span data-stu-id="17d06-107">If there is a white space character following the delimiter, that character is not included in the XML output.</span></span>

  > [!NOTE]
  > <span data-ttu-id="17d06-108">Il Integrated Development Environment (IDE) di Visual Studio inserisce automaticamente `<summary>` i `</summary>` tag e e sposta il cursore all'interno di questi tag dopo aver digitato il `///` delimitatore nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="17d06-108">The Visual Studio integrated development environment (IDE) automatically inserts the `<summary>` and `</summary>` tags and moves your cursor within these tags after you type the `///` delimiter in the code editor.</span></span> <span data-ttu-id="17d06-109">È possibile attivare o disattivare questa funzionalità nella [finestra di dialogo Opzioni](/visualstudio/ide/reference/options-text-editor-csharp-advanced).</span><span class="sxs-lookup"><span data-stu-id="17d06-109">You can turn this feature on or off in the [Options dialog box](/visualstudio/ide/reference/options-text-editor-csharp-advanced).</span></span>
  
- `/** */`

  <span data-ttu-id="17d06-110">Delimitatori di più righe.</span><span class="sxs-lookup"><span data-stu-id="17d06-110">Multiline delimiters.</span></span>

  <span data-ttu-id="17d06-111">Quando si usano i delimitatori, è necessario seguire alcune regole di formattazione `/** */` :</span><span class="sxs-lookup"><span data-stu-id="17d06-111">There are some formatting rules to follow when you use the `/** */` delimiters:</span></span>
  
  - <span data-ttu-id="17d06-112">Nella riga contenente il delimitatore `/**` se la parte restante della riga è rappresentata da uno spazio vuoto, la riga non viene elaborata per i commenti.</span><span class="sxs-lookup"><span data-stu-id="17d06-112">On the line that contains the `/**` delimiter, if the remainder of the line is white space, the line is not processed for comments.</span></span> <span data-ttu-id="17d06-113">Se il primo carattere dopo il delimitatore `/**` è uno spazio vuoto, lo spazio vuoto viene ignorato e il resto della riga viene elaborato.</span><span class="sxs-lookup"><span data-stu-id="17d06-113">If the first character after the `/**` delimiter is white space, that white space character is ignored and the rest of the line is processed.</span></span> <span data-ttu-id="17d06-114">In caso contrario, l'intero testo della riga dopo il delimitatore `/**` viene elaborato come parte del commento.</span><span class="sxs-lookup"><span data-stu-id="17d06-114">Otherwise, the entire text of the line after the `/**` delimiter is processed as part of the comment.</span></span>

  - <span data-ttu-id="17d06-115">Se sulla riga contenente il delimitatore `*/` sono presenti solo spazi vuoti fino al delimitatore `*/`, la riga viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="17d06-115">On the line that contains the `*/` delimiter, if there is only white space up to the `*/` delimiter, that line is ignored.</span></span> <span data-ttu-id="17d06-116">In caso contrario, il testo nella riga fino al `*/` delimitatore viene elaborato come parte del commento.</span><span class="sxs-lookup"><span data-stu-id="17d06-116">Otherwise, the text on the line up to the `*/` delimiter is processed as part of the comment.</span></span>
  
  - <span data-ttu-id="17d06-117">Per le righe successive a quella che inizia con il delimitatore `/**`, il compilatore cerca un modello comune all'inizio di ogni riga.</span><span class="sxs-lookup"><span data-stu-id="17d06-117">For the lines after the one that begins with the `/**` delimiter, the compiler looks for a common pattern at the beginning of each line.</span></span> <span data-ttu-id="17d06-118">Il modello può essere costituito da uno spazio vuoto facoltativo e un asterisco (`*`) seguiti da altri spazi vuoti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="17d06-118">The pattern can consist of optional white space and an asterisk (`*`), followed by more optional white space.</span></span> <span data-ttu-id="17d06-119">Se trova un modello comune all'inizio di ogni riga che non inizia con il delimitatore `/**` o `*/`, il compilatore ignora tale modello per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="17d06-119">If the compiler finds a common pattern at the beginning of each line that does not begin with the `/**` delimiter or the `*/` delimiter, it ignores that pattern for each line.</span></span>

  <span data-ttu-id="17d06-120">Gli esempi seguenti illustrano queste regole.</span><span class="sxs-lookup"><span data-stu-id="17d06-120">The following examples illustrate these rules.</span></span>

  - <span data-ttu-id="17d06-121">L'unica parte del commento seguente elaborato è la riga che inizia con `<summary>` .</span><span class="sxs-lookup"><span data-stu-id="17d06-121">The only part of the following comment that's processed is the line that begins with `<summary>`.</span></span> <span data-ttu-id="17d06-122">I tre formati di tag producono gli stessi commenti.</span><span class="sxs-lookup"><span data-stu-id="17d06-122">The three tag formats produce the same comments.</span></span>

    ```csharp
    /** <summary>text</summary> */

    /**
    <summary>text</summary>
    */

    /**
     * <summary>text</summary>
    */
    ```

  - <span data-ttu-id="17d06-123">Il compilatore identifica un modello comune di " \* " all'inizio della seconda e della terza riga.</span><span class="sxs-lookup"><span data-stu-id="17d06-123">The compiler identifies a common pattern of " \* " at the beginning of the second and third lines.</span></span> <span data-ttu-id="17d06-124">Il modello non è incluso nell'output.</span><span class="sxs-lookup"><span data-stu-id="17d06-124">The pattern is not included in the output.</span></span>

    ```csharp
    /**
     * <summary>
     * text </summary>*/
    ```

  - <span data-ttu-id="17d06-125">Il compilatore non trova alcun modello comune nel commento seguente poiché il secondo carattere nella terza riga non è un asterisco.</span><span class="sxs-lookup"><span data-stu-id="17d06-125">The compiler finds no common pattern in the following comment because the second character on the third line is not an asterisk.</span></span> <span data-ttu-id="17d06-126">Di conseguenza, tutto il testo contenuto nella seconda e nella terza riga viene elaborato come parte del commento.</span><span class="sxs-lookup"><span data-stu-id="17d06-126">Therefore, all text on the second and third lines is processed as part of the comment.</span></span>

    ```csharp
    /**
     * <summary>
       text </summary>
    */
    ```

  - <span data-ttu-id="17d06-127">Nel commento seguente il compilatore non rileva alcun modello per due motivi.</span><span class="sxs-lookup"><span data-stu-id="17d06-127">The compiler finds no pattern in the following comment for two reasons.</span></span> <span data-ttu-id="17d06-128">In primo luogo, il numero di spazi prima dell'asterisco non è coerente.</span><span class="sxs-lookup"><span data-stu-id="17d06-128">First, the number of spaces before the asterisk is not consistent.</span></span> <span data-ttu-id="17d06-129">In secondo luogo, la quinta riga inizia con una tabulazione senza corrispondenza degli spazi.</span><span class="sxs-lookup"><span data-stu-id="17d06-129">Second, the fifth line begins with a tab, which does not match spaces.</span></span> <span data-ttu-id="17d06-130">Di conseguenza, tutto il testo dalla seconda alla quinta riga verrà elaborato come parte del commento.</span><span class="sxs-lookup"><span data-stu-id="17d06-130">Therefore, all text from lines two through five is processed as part of the comment.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="17d06-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17d06-131">See also</span></span>

- [<span data-ttu-id="17d06-132">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="17d06-132">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="17d06-133">Commenti relativi alla documentazione XML</span><span class="sxs-lookup"><span data-stu-id="17d06-133">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="17d06-134">-DOC (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="17d06-134">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
