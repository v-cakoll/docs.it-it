---
title: 'Procedura: accedere ai membri di un oggetto (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: 62be2955bd1f62fa5af4e54fb0af5e7dca29c421
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650921"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Procedura: accedere ai membri di un oggetto (Visual Basic)
Quando si dispone di una variabile oggetto che fa riferimento a un oggetto, spesso si desidera lavorare con i membri di tale oggetto, ad esempio i relativi metodi, proprietà, campi ed eventi. Ad esempio, dopo aver creato un nuovo <xref:System.Windows.Forms.Form> dell'oggetto, è possibile impostare il relativo <xref:System.Windows.Forms.Control.Text%2A> chiamata o proprietà relativo <xref:System.Windows.Forms.Control.Focus%2A> (metodo).  
  
## <a name="accessing-members"></a>L'accesso ai membri  
 Membri di un oggetto sono accessibili tramite la variabile che fa riferimento a esso.  
  
#### <a name="to-access-members-of-an-object"></a>Per accedere ai membri di un oggetto  
  
-   Usare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     Se il membro è [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), non è necessaria una variabile per accedervi.  
  
## <a name="accessing-members-of-an-object-of-known-type"></a>L'accesso ai membri di un oggetto di tipo noto  
 Se si conosce il tipo di un oggetto in fase di compilazione, è possibile utilizzare *associazione anticipata* per una variabile che fa riferimento a esso.  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Per accedere ai membri di un oggetto per cui si conosce il tipo in fase di compilazione  
  
1.  Dichiarare la variabile di oggetto di tipo dell'oggetto a cui che si desidera assegnare alla variabile.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     Con `Option Strict On`, è possibile assegnare solo <xref:System.Windows.Forms.Form> oggetti (o gli oggetti di un tipo derivato da <xref:System.Windows.Forms.Form>) a `extraForm`. Se si è definite una classe o struttura con un ampliamento `CType` conversione <xref:System.Windows.Forms.Form>, è inoltre possibile assegnare la classe o struttura in `extraForm`.  
  
2.  Usare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.  
  
    ```  
    extraForm.Show()  
    ```  
  
     È possibile accedere a tutti i metodi e proprietà specifiche per la <xref:System.Windows.Forms.Form> (classe), indipendentemente il `Option Strict` impostazione.  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a>L'accesso ai membri di un oggetto di tipo sconosciuto  
 Se non si conosce il tipo di un oggetto in fase di compilazione, è necessario utilizzare *ad associazione tardiva* per qualsiasi variabile che fa riferimento a esso.  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Per accedere ai membri di un oggetto per cui non si conosce il tipo in fase di compilazione  
  
1.  Dichiarare la variabile di oggetto di [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md). (La dichiarazione di una variabile come `Object` corrisponde alla dichiarazione come <xref:System.Object?displayProperty=nameWithType>.)  
  
    ```  
    Dim someControl As Object  
    ```  
  
     Con `Option Strict On`, è possibile accedere solo i membri che sono definiti nella <xref:System.Object> classe.  
  
2.  Usare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.  
  
    ```  
    someControl.GetType()  
    ```  
  
     Per essere in grado di accedere ai membri di qualsiasi oggetto assegnato alla variabile oggetto, è necessario impostare `Option Strict Off`. Quando si esegue questa operazione, il compilatore non garantisce che un determinato membro viene esposto da oggetto assegnato alla variabile. Se l'oggetto non espone un membro a cui si tenta di accedere, un <xref:System.MemberAccessException> si verifica un'eccezione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Object>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.MemberAccessException>  
 [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Dichiarazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
