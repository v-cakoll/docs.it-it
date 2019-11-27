---
title: 'Procedura: accedere ai membri di un oggetto'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: d44b538e8413eb1412e937375e9bca77600a29b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348660"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Procedura: accedere ai membri di un oggetto (Visual Basic)

Quando si dispone di una variabile oggetto che fa riferimento a un oggetto, spesso si desidera lavorare con i membri di tale oggetto, ad esempio i metodi, le proprietà, i campi e gli eventi. Ad esempio, dopo aver creato un nuovo <xref:System.Windows.Forms.Form> oggetto, potrebbe essere necessario impostare la relativa proprietà <xref:System.Windows.Forms.Control.Text%2A> o chiamare il relativo metodo <xref:System.Windows.Forms.Control.Focus%2A>.

## <a name="accessing-members"></a>Accesso ai membri

È possibile accedere ai membri di un oggetto tramite la variabile che vi fa riferimento.

#### <a name="to-access-members-of-an-object"></a>Per accedere ai membri di un oggetto

- Utilizzare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.

    ```vb
    currentText = newForm.Text
    ```

    Se il membro è [condiviso](../../../../visual-basic/language-reference/modifiers/shared.md), non è necessaria una variabile per accedervi.

## <a name="accessing-members-of-an-object-of-known-type"></a>Accesso ai membri di un oggetto di tipo noto

Se si conosce il tipo di un oggetto in fase di compilazione, è possibile usare l' *associazione anticipata* per una variabile che vi fa riferimento.

#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Per accedere ai membri di un oggetto per il quale si conosce il tipo in fase di compilazione

1. Dichiarare la variabile oggetto in modo che sia del tipo dell'oggetto che si intende assegnare alla variabile.

    ```vb
    Dim extraForm As System.Windows.Forms.Form
    ```

    Con `Option Strict On`è possibile assegnare a `extraForm`solo oggetti <xref:System.Windows.Forms.Form> (o oggetti di un tipo derivato da <xref:System.Windows.Forms.Form>). Se è stata definita una classe o una struttura con una conversione di `CType` verso un tipo di dati più ampio a <xref:System.Windows.Forms.Form>, è anche possibile assegnare tale classe o struttura a `extraForm`.

2. Utilizzare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.

    ```vb
    extraForm.Show()
    ```

    È possibile accedere a tutti i metodi e le proprietà specifici della classe <xref:System.Windows.Forms.Form>, a prescindere dall'impostazione del `Option Strict`.

## <a name="accessing-members-of-an-object-of-unknown-type"></a>Accesso ai membri di un oggetto di tipo sconosciuto

Se non si conosce il tipo di un oggetto in fase di compilazione, è necessario usare l' *associazione tardiva* per qualsiasi variabile che vi faccia riferimento.

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Per accedere ai membri di un oggetto per il quale non si conosce il tipo in fase di compilazione

1. Dichiarare la variabile oggetto in modo che sia del [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md). (Dichiarando una variabile come `Object` è uguale a dichiararlo come <xref:System.Object?displayProperty=nameWithType>).

    ```vb
    Dim someControl As Object
    ```

    Con `Option Strict On`, è possibile accedere solo ai membri definiti nella classe <xref:System.Object>.

2. Utilizzare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.

    ```vb
    someControl.GetType()
    ```

    Per poter accedere ai membri di qualsiasi oggetto assegnato alla variabile oggetto, è necessario impostare `Option Strict Off`. Quando si esegue questa operazione, il compilatore non può garantire che un determinato membro venga esposto dall'oggetto assegnato alla variabile. Se l'oggetto non espone un membro a cui si tenta di accedere, si verifica un'eccezione <xref:System.MemberAccessException>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Dichiarazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
