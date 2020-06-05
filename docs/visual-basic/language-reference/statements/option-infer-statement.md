---
title: Option Infer (istruzione)
ms.date: 07/20/2015
f1_keywords:
- vb.OptionInfer
- vb.Infer
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement [Visual Basic]
- Infer keyword [Visual Basic]
- declaring variables [Visual Basic], inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
ms.openlocfilehash: 977e492c1c8ec5040c22169d91268c9c2241f6c4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404356"
---
# <a name="option-infer-statement"></a>Option Infer (istruzione)

Abilita l'uso dell'inferenza del tipo di variabile locale nelle variabili dichiaranti.

## <a name="syntax"></a>Sintassi

```vb
Option Infer { On | Off }
```

## <a name="parts"></a>Parti

|Termine|Definizione|
|---|---|
|`On`|Facoltativa. Abilita l'inferenza del tipo di variabile locale.|
|`Off`|Facoltativa. Disabilita l'inferenza del tipo di variabile locale.|

## <a name="remarks"></a>Commenti

Per impostare `Option Infer` in un file, digitare `Option Infer On` oppure `Option Infer Off` all'inizio del file, prima di qualsiasi altro codice sorgente. Se il valore impostato per `Option Infer` in un file è in conflitto con il valore impostato nell'IDE o sulla riga di comando, il valore nel file ha precedenza.

Quando si imposta `Option Infer` su `On`, è possibile dichiarare variabili locali senza dichiarare in modo esplicito un tipo di dati. Tramite l'inferenza, il compilatore deriva il tipo di dati di una variabile dal tipo della relativa espressione di inizializzazione.

Nella figura seguente, l'istruzione `Option Infer` è abilitata. La variabile nella dichiarazione `Dim someVar = 2` viene dichiarata come Integer in base all'inferenza del tipo.

La schermata seguente mostra IntelliSense quando Option deduce è on:

![Screenshot che mostra la visualizzazione IntelliSense quando Option deduce è on.](./media/option-infer-statement/option-infer-as-integer-on.png)

Nella figura seguente, l'istruzione `Option Infer` è disabilitata. La variabile nella dichiarazione `Dim someVar = 2` viene dichiarata come `Object` in base all'inferenza del tipo. In questo esempio, l'impostazione **Option Strict** è impostata su **off** nella [pagina compila, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).

La schermata seguente mostra IntelliSense quando Option dedurre è disattivato:

![Screenshot che mostra la visualizzazione IntelliSense quando l'opzione deduce è disattivata.](./media/option-infer-statement/option-infer-as-object-off.png)

> [!NOTE]
> Quando una variabile viene dichiarata come `Object`, il tipo di runtime può essere modificato mentre il programma è in esecuzione. Visual Basic esegue operazioni denominate *Boxing* e *unboxing per eseguire* la conversione tra un oggetto `Object` e un tipo di valore, il che rende l'esecuzione più lenta. Per informazioni su conversione boxing e unboxing, vedere la [specifica del linguaggio Visual Basic](~/_vblang/spec/conversions.md#value-type-conversions).

L'inferenza del tipo si applica a livello di routine e non si applica all'esterno di una routine in una classe, una struttura, un modulo o un'interfaccia.

Per altre informazioni, vedere [inferenza dei tipi locali](../../programming-guide/language-features/variables/local-type-inference.md).

## <a name="when-an-option-infer-statement-is-not-present"></a>Quando non è presente un'istruzione Option Infer

Se il codice sorgente non contiene un' `Option Infer` istruzione, viene utilizzata l' **opzione deduce** impostazione nella [pagina Compila, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) . Se viene usato il compilatore da riga di comando, viene usata l'opzione del compilatore [-optioninfer (](../../reference/command-line-compiler/optioninfer.md) .

#### <a name="to-set-option-infer-in-the-ide"></a>Per impostare Option Infer nell'IDE

1. In **Esplora soluzioni**selezionare un progetto. Scegliere **Proprietà** dal menu **Progetto**.

2. Fare clic sulla scheda **Compila**.

3. Impostare il valore nella casella **Option dedurre** .

Quando si crea un nuovo progetto, l'impostazione **Option deduce** nella scheda **Compila** viene impostata sull'impostazione **Option dedurre** nella finestra di dialogo **impostazioni predefinite di Visual Basic** . Per accedere alla finestra di dialogo **impostazioni predefinite di Visual Basic** , scegliere **Opzioni**dal menu **strumenti** . Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**. L'impostazione predefinita iniziale in impostazioni **predefinite di Visual Basic** è `On` .

#### <a name="to-set-option-infer-on-the-command-line"></a>Per impostare Option Infer nella riga di comando

Includere l'opzione del compilatore [-optioninfer (](../../reference/command-line-compiler/optioninfer.md) nel comando **vbc** .

## <a name="default-data-types-and-values"></a>Tipi di dati e valori predefiniti

Nella tabella seguente vengono descritti i risultati di varie combinazioni della specifica del tipo di dati e dell'inizializzatore in un'istruzione `Dim`.

|Tipo di dati specificato?|Inizializzatore specificato?|Esempio|Risultato|
|---|---|---|---|
|No|No|`Dim qty`|Se `Option Strict` è disabilitato (impostazione predefinita), la variabile è impostata su `Nothing`.<br /><br /> Se `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|
|No|Sì|`Dim qty = 5`|Se `Option Infer` è abilitato (impostazione predefinita), alla variabile viene assegnato il tipo di dati dell'inizializzatore. Vedere [inferenza del tipo locale](../../programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Se le istruzioni `Option Infer` e `Option Strict` sono disabilitate, il tipo di dati accettato dalla variabile è `Object`.<br /><br /> Se `Option Infer` è disabilitato e `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|
|Sì|No|`Dim qty As Integer`|La variabile viene inizializzata sul valore predefinito per il tipo di dati. Per ulteriori informazioni, vedere [istruzione Dim](dim-statement.md).|
|Sì|Sì|`Dim qty  As Integer = 5`|Se il tipo di dati dell'inizializzatore non è convertibile nel tipo di dati specificato, si verifica un errore in fase di compilazione.|

## <a name="example"></a>Esempio

Gli esempi seguenti illustrano come l'istruzione `Option Infer` permette di usare inferenza del tipo di variabile locale.

[!code-vb[VbVbalrTypeInference#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#6)]

## <a name="example"></a>Esempio

L'esempio seguente dimostra che il tipo di runtime può differire quando una variabile viene identificata come `Object`.

[!code-vb[VbVbalrTypeInference#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#11)]

## <a name="see-also"></a>Vedere anche

- [Istruzione Dim](dim-statement.md)
- [Inferenza del tipo di variabile locale](../../programming-guide/language-features/variables/local-type-inference.md)
- [Istruzione Option Compare](option-compare-statement.md)
- [Istruzione Option Explicit](option-explicit-statement.md)
- [Option Strict Statement](option-strict-statement.md)
- [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [-optioninfer](../../reference/command-line-compiler/optioninfer.md)
- [Conversione boxing e unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
