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
ms.openlocfilehash: 53bc9d41f28f63061db2012395480aa6be7515dd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346489"
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
|`On`|Parametro facoltativo. Abilita l'inferenza del tipo di variabile locale.|
|`Off`|Parametro facoltativo. Disabilita l'inferenza del tipo di variabile locale.|

## <a name="remarks"></a>Note

Per impostare `Option Infer` in un file, digitare `Option Infer On` oppure `Option Infer Off` all'inizio del file, prima di qualsiasi altro codice sorgente. Se il valore impostato per `Option Infer` in un file è in conflitto con il valore impostato nell'IDE o sulla riga di comando, il valore nel file ha precedenza.

Quando si imposta `Option Infer` su `On`, è possibile dichiarare variabili locali senza dichiarare in modo esplicito un tipo di dati. Tramite l'inferenza, il compilatore deriva il tipo di dati di una variabile dal tipo della relativa espressione di inizializzazione.

Nella figura seguente, l'istruzione `Option Infer` è abilitata. La variabile nella dichiarazione `Dim someVar = 2` viene dichiarata come Integer in base all'inferenza del tipo.

The following screenshot shows IntelliSense when Option Infer is on:

![Screenshot showing IntelliSense view when Option Infer is on.](./media/option-infer-statement/option-infer-as-integer-on.png)

Nella figura seguente, l'istruzione `Option Infer` è disabilitata. La variabile nella dichiarazione `Dim someVar = 2` viene dichiarata come `Object` in base all'inferenza del tipo. In this example, the **Option Strict** setting is set to **Off** on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).

The following screenshot shows IntelliSense when Option Infer is off:

![Screenshot showing IntelliSense view when Option Infer is off.](./media/option-infer-statement/option-infer-as-object-off.png)

> [!NOTE]
> Quando una variabile viene dichiarata come `Object`, il tipo di runtime può essere modificato mentre il programma è in esecuzione. Visual Basic performs operations called *boxing* and *unboxing* to convert between an `Object` and a value type, which makes execution slower. For information about boxing and unboxing, see the [Visual Basic Language Specification](~/_vblang/spec/conversions.md#value-type-conversions).

L'inferenza del tipo si applica a livello di routine e non si applica all'esterno di una routine in una classe, una struttura, un modulo o un'interfaccia.

For additional information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).

## <a name="when-an-option-infer-statement-is-not-present"></a>Quando non è presente un'istruzione Option Infer

If the source code does not contain an `Option Infer` statement, the **Option Infer** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used. If the command-line compiler is used, the [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option is used.

#### <a name="to-set-option-infer-in-the-ide"></a>Per impostare Option Infer nell'IDE

1. Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.

2. Fare clic sulla scheda **Compila**.

3. Set the value in the **Option infer** box.

When you create a new project, the **Option Infer** setting on the **Compile** tab is set to the **Option Infer** setting in the **VB Defaults** dialog box. To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**. Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**. The initial default setting in **VB Defaults** is `On`.

#### <a name="to-set-option-infer-on-the-command-line"></a>Per impostare Option Infer nella riga di comando

Include the [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option in the **vbc** command.

## <a name="default-data-types-and-values"></a>Tipi di dati e valori predefiniti

Nella tabella seguente vengono descritti i risultati di varie combinazioni della specifica del tipo di dati e dell'inizializzatore in un'istruzione `Dim`.

|Tipo di dati specificato?|Inizializzatore specificato?|Esempio|Risultato|
|---|---|---|---|
|No|No|`Dim qty`|Se `Option Strict` è disabilitato (impostazione predefinita), la variabile è impostata su `Nothing`.<br /><br /> Se `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|
|No|Yes|`Dim qty = 5`|Se `Option Infer` è abilitato (impostazione predefinita), alla variabile viene assegnato il tipo di dati dell'inizializzatore. See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Se le istruzioni `Option Infer` e `Option Strict` sono disabilitate, il tipo di dati accettato dalla variabile è `Object`.<br /><br /> Se `Option Infer` è disabilitato e `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|
|Yes|No|`Dim qty As Integer`|La variabile viene inizializzata sul valore predefinito per il tipo di dati. For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).|
|Yes|Yes|`Dim qty  As Integer = 5`|Se il tipo di dati dell'inizializzatore non è convertibile nel tipo di dati specificato, si verifica un errore in fase di compilazione.|

## <a name="example"></a>Esempio

Gli esempi seguenti illustrano come l'istruzione `Option Infer` permette di usare inferenza del tipo di variabile locale.

[!code-vb[VbVbalrTypeInference#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#6)]

## <a name="example"></a>Esempio

L'esempio seguente dimostra che il tipo di runtime può differire quando una variabile viene identificata come `Object`.

[!code-vb[VbVbalrTypeInference#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#11)]

## <a name="see-also"></a>Vedere anche

- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Boxing e unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
