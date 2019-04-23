---
title: 'Procedura: Accedere ai membri di un oggetto (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: de00e428cc3d9d7a5688e853b0ff4295fec5b3e9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322758"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Procedura: Accedere ai membri di un oggetto (Visual Basic)
Quando si dispone di una variabile oggetto che fa riferimento a un oggetto, è spesso necessario lavorare con i membri di tale oggetto, ad esempio relativi metodi, proprietà, campi ed eventi. Ad esempio, dopo aver creato un nuovo <xref:System.Windows.Forms.Form> dell'oggetto, si potrebbe voler impostare relativi <xref:System.Windows.Forms.Control.Text%2A> proprietà o chiamata relativo <xref:System.Windows.Forms.Control.Focus%2A> (metodo).  
  
## <a name="accessing-members"></a>L'accesso ai membri  
 Membri di un oggetto si accede tramite la variabile che vi fa riferimento.  
  
#### <a name="to-access-members-of-an-object"></a>Per accedere ai membri di un oggetto  
  
-   Usare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     Se il membro [condiviso](../../../../visual-basic/language-reference/modifiers/shared.md), non è necessaria una variabile per accedervi.  
  
## <a name="accessing-members-of-an-object-of-known-type"></a>L'accesso ai membri di un oggetto di tipo conosciuto  
 Se si conosce il tipo di un oggetto in fase di compilazione, è possibile usare *associazione anticipata* per una variabile che vi fa riferimento.  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Per accedere ai membri di un oggetto per cui si conosce il tipo in fase di compilazione  
  
1. Dichiarare la variabile oggetto di tipo dell'oggetto che si intende assegnare alla variabile.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     Con `Option Strict On`, è possibile assegnare solo <xref:System.Windows.Forms.Form> oggetti (o gli oggetti di un tipo derivato da <xref:System.Windows.Forms.Form>) a `extraForm`. Se è stato definito una classe o struttura con un ampliamento `CType` conversione <xref:System.Windows.Forms.Form>, è anche possibile assegnare tale classe o struttura a `extraForm`.  
  
2. Usare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.  
  
    ```  
    extraForm.Show()  
    ```  
  
     È possibile accedere a tutti i metodi e proprietà specifiche per il <xref:System.Windows.Forms.Form> (classe), indipendentemente il `Option Strict` impostazione.  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a>L'accesso ai membri di un oggetto di tipo sconosciuto  
 Se non si conosce il tipo di un oggetto in fase di compilazione, è necessario utilizzare *associazione tardiva* per qualsiasi variabile che vi fa riferimento.  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Per accedere ai membri di un oggetto per cui non si conosce il tipo in fase di compilazione  
  
1. Dichiarare la variabile di oggetto di [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md). (Dichiarazione di una variabile come `Object` equivale dichiararla come <xref:System.Object?displayProperty=nameWithType>.)  
  
    ```  
    Dim someControl As Object  
    ```  
  
     Con `Option Strict On`, è possibile accedere solo i membri che sono definiti nel <xref:System.Object> classe.  
  
2. Usare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.  
  
    ```  
    someControl.GetType()  
    ```  
  
     Per poter accedere ai membri di qualsiasi oggetto assegnato alla variabile di oggetto, è necessario impostare `Option Strict Off`. Quando si esegue questa operazione, il compilatore non può garantire che un determinato membro viene esposta dall'oggetto a cui che si assegna alla variabile. Se l'oggetto non espone un membro a cui si tenta di accedere, un <xref:System.MemberAccessException> si verifica un'eccezione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Dichiarazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
