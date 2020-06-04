---
title: 'Procedura: accedere ai membri di un oggetto'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: 2826a3c98b9f19b08cc943d0f67cdd34ac90f526
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410542"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Procedura: accedere ai membri di un oggetto (Visual Basic)

Quando si dispone di una variabile oggetto che fa riferimento a un oggetto, spesso si desidera lavorare con i membri di tale oggetto, ad esempio i metodi, le proprietà, i campi e gli eventi. Ad esempio, dopo aver creato un nuovo <xref:System.Windows.Forms.Form> oggetto, potrebbe essere necessario impostare la relativa <xref:System.Windows.Forms.Control.Text%2A> proprietà o chiamarne il <xref:System.Windows.Forms.Control.Focus%2A> metodo.

## <a name="accessing-members"></a>Accesso ai membri

È possibile accedere ai membri di un oggetto tramite la variabile che vi fa riferimento.

#### <a name="to-access-members-of-an-object"></a>Per accedere ai membri di un oggetto

- Utilizzare l'operatore di accesso ai membri ( `.` ) tra il nome della variabile oggetto e il nome del membro.

    ```vb
    currentText = newForm.Text
    ```

    Se il membro è [condiviso](../../../language-reference/modifiers/shared.md), non è necessaria una variabile per accedervi.

## <a name="accessing-members-of-an-object-of-known-type"></a>Accesso ai membri di un oggetto di tipo noto

Se si conosce il tipo di un oggetto in fase di compilazione, è possibile usare l' *associazione anticipata* per una variabile che vi fa riferimento.

#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Per accedere ai membri di un oggetto per il quale si conosce il tipo in fase di compilazione

1. Dichiarare la variabile oggetto in modo che sia del tipo dell'oggetto che si intende assegnare alla variabile.

    ```vb
    Dim extraForm As System.Windows.Forms.Form
    ```

    Con `Option Strict On` è possibile assegnare solo <xref:System.Windows.Forms.Form> oggetti (o oggetti di un tipo derivato da <xref:System.Windows.Forms.Form> ) a `extraForm` . Se è stata definita una classe o una struttura con una conversione verso un tipo di dati più ampio `CType` <xref:System.Windows.Forms.Form> , è anche possibile assegnare tale classe o struttura a `extraForm` .

2. Utilizzare l'operatore di accesso ai membri ( `.` ) tra il nome della variabile oggetto e il nome del membro.

    ```vb
    extraForm.Show()
    ```

    È possibile accedere a tutti i metodi e le proprietà specifici della <xref:System.Windows.Forms.Form> classe, a prescindere dall' `Option Strict` impostazione.

## <a name="accessing-members-of-an-object-of-unknown-type"></a>Accesso ai membri di un oggetto di tipo sconosciuto

Se non si conosce il tipo di un oggetto in fase di compilazione, è necessario usare l' *associazione tardiva* per qualsiasi variabile che vi faccia riferimento.

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Per accedere ai membri di un oggetto per il quale non si conosce il tipo in fase di compilazione

1. Dichiarare la variabile oggetto in modo che sia del [tipo di dati Object](../../../language-reference/data-types/object-data-type.md). (Dichiarando una variabile come `Object` la dichiarata come <xref:System.Object?displayProperty=nameWithType> ).

    ```vb
    Dim someControl As Object
    ```

    Con `Option Strict On` , è possibile accedere solo ai membri definiti nella <xref:System.Object> classe.

2. Utilizzare l'operatore di accesso ai membri ( `.` ) tra il nome della variabile oggetto e il nome del membro.

    ```vb
    someControl.GetType()
    ```

    Per poter accedere ai membri di qualsiasi oggetto assegnato alla variabile oggetto, è necessario impostare `Option Strict Off` . Quando si esegue questa operazione, il compilatore non può garantire che un determinato membro venga esposto dall'oggetto assegnato alla variabile. Se l'oggetto non espone un membro a cui si tenta di accedere, <xref:System.MemberAccessException> si verificherà un'eccezione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [Variabili oggetto](object-variables.md)
- [Dichiarazione di variabili oggetto](object-variable-declaration.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)
