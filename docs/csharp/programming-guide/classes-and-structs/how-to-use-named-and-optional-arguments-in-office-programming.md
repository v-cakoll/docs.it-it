---
title: Come usare gli argomenti denominati e facoltativi nella programmazione di Office - Guida per programmatori C
ms.date: 07/20/2015
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
ms.openlocfilehash: 36b5c8b49404606c8240d24953c3677d5612d30e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714867"
---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a>Come usare gli argomenti denominati e facoltativi nella programmazione di Office (Guida per programmatori C

Gli argomenti denominati e gli argomenti facoltativi, introdotti in C# 4, migliorano la praticità, la flessibilità e la leggibilità nella programmazione C#. Queste funzionalità, poi, semplificano notevolmente l'accesso alle interfacce COM, quali le API di automazione di Microsoft Office.

Nell'esempio seguente, il metodo [ConvertToTable](<xref:Microsoft.Office.Interop.Word.Range.ConvertToTable%2A>) dispone di sedici parametri che rappresentano le caratteristiche di una tabella, ad esempio il numero di colonne e di righe, la formattazione, i bordi, i tipi di carattere e i colori. I sedici parametri sono tutti facoltativi, perché nella maggior parte dei casi non si vogliono specificare particolari valori per tutti. Senza gli argomenti denominati e facoltativi, tuttavia, è necessario specificare un valore o un valore di segnaposto per ogni parametro. Con gli argomenti denominati e facoltativi si specificano valori solo per i parametri obbligatori per il progetto.

Per eseguire queste procedure, Microsoft Office Word deve essere installato.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-new-console-application"></a>Per creare un nuovo progetto di applicazione console

1. Avviare Visual Studio.

2. Scegliere **Nuovo** dal menu **File**e quindi fare clic su **Progetto**.

3. Nel riquadro **Categorie di modelli** espandere **Visual C#** e quindi fare clic su **Windows**.

4. Verificare che nella parte superiore del riquadro **Modelli** sia visualizzato **.NET Framework 4** nella casella **Framework di destinazione**.

5. Nel riquadro **Modelli** fare clic su **Applicazione console**.

6. Digitare un nome per il progetto nel campo **Nome**.

7. Fare clic su **OK**.

     Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.

## <a name="to-add-a-reference"></a>Per aggiungere un riferimento

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nome del progetto e quindi scegliere **Aggiungi riferimento**. Verrà visualizzata la finestra di dialogo **Aggiungi riferimento**.

2. Nella pagina **.NET** selezionare **Microsoft.Office.Interop.Word** nell'elenco **Nome componente**.

3. Fare clic su **OK**.

## <a name="to-add-necessary-using-directives"></a>Per aggiungere le direttive using necessarie

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file *Program.cs* e quindi fare clic su **Visualizza codice**.

2. Aggiungere le `using` direttive seguenti all'inizio del file di codice:

     [!code-csharp[csProgGuideNamedAndOptional#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#4)]

## <a name="to-display-text-in-a-word-document"></a>Per visualizzare il testo in un documento di Word

1. Nella `Program` classe *in Program.cs*aggiungere il metodo seguente per creare un'applicazione Word e un documento di Word. Il metodo [Add](<xref:Microsoft.Office.Interop.Word.Documents.Add%2A>) dispone di quattro parametri facoltativi. Questo esempio usa i relativi valori predefiniti. Non sono pertanto necessari argomenti nell'istruzione di chiamata.

     [!code-csharp[csProgGuideNamedAndOptional#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#6)]

2. Aggiungere il codice seguente alla fine del metodo per definire dove visualizzare il testo nel documento e il testo da visualizzare:

     [!code-csharp[csProgGuideNamedAndOptional#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#7)]

## <a name="to-run-the-application"></a>Per eseguire l'applicazione

1. Aggiungere la seguente istruzione a Main:

     [!code-csharp[csProgGuideNamedAndOptional#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#8)]

2. Premere <kbd>CTRL</kbd>+<kbd>F5</kbd> per eseguire il progetto. Verrà visualizzato un documento di Word contenente il testo specificato.

## <a name="to-change-the-text-to-a-table"></a>Per convertire il testo in una tabella
  
1. Usare il metodo `ConvertToTable` per racchiudere il testo in una tabella. Il metodo ha 16 parametri facoltativi. IntelliSense racchiude tra parentesi quadre i parametri facoltativi, come mostrato nell'immagine seguente.

     ![Elenco dei parametri del metodo ConvertToTable](./media/how-to-use-named-and-optional-arguments-in-office-programming/convert-table-parameters.png)

     Gli argomenti denominati e facoltativi consentono di specificare valori esclusivamente per i parametri che si vogliono modificare. Aggiungere il codice seguente alla fine del metodo `DisplayInWord` per creare una tabella semplice. L'argomento indica che le virgole nella stringa di testo in `range` separano le celle della tabella.

     [!code-csharp[csProgGuideNamedAndOptional#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#9)]

     Nelle versioni precedenti di C, `ConvertToTable` la chiamata a richiede un argomento di riferimento per ogni parametro, come illustrato nel codice seguente:
  
     [!code-csharp[csProgGuideNamedAndOptional#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#14)]

2. Premere <kbd>CTRL</kbd>+<kbd>F5</kbd> per eseguire il progetto.

## <a name="to-experiment-with-other-parameters"></a>Per provare a usare altri parametri

1. Per modificare la tabella in modo che condisponga di `DisplayInWord` una colonna e tre righe, sostituire l'ultima riga con l'istruzione seguente e quindi digitare <kbd>CTRL</kbd>+<kbd>F5</kbd>.  

     [!code-csharp[csProgGuideNamedAndOptional#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#10)]

2. Per specificare un formato predefinito per la `DisplayInWord` tabella, sostituire l'ultima riga con l'istruzione seguente, quindi digitare <kbd>CTRL</kbd>+<kbd>F5.</kbd> Il formato può corrispondere a qualsiasi costante [WdTableFormat](<xref:Microsoft.Office.Interop.Word.WdTableFormat>).

     [!code-csharp[csProgGuideNamedAndOptional#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#11)]

## <a name="example"></a>Esempio

Il codice seguente include l'esempio completo:The following code includes the full example:

 [!code-csharp[csProgGuideNamedAndOptional#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#12)]

## <a name="see-also"></a>Vedere anche

- [Argomenti denominati e facoltativi](./named-and-optional-arguments.md)
