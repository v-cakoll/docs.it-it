---
title: Istruzione Option Explicit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
ms.openlocfilehash: 3a2d81b1441052c132e4739dfe6045f8c3a026d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604601"
---
# <a name="option-explicit-statement-visual-basic"></a>Istruzione Option Explicit (Visual Basic)
Forza la dichiarazione esplicita di tutte le variabili in un file o consente dichiarazioni implicite delle variabili.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Parti  
 `On`  
 Facoltativo. Abilita `Option Explicit` il controllo. Se `On` o `Off` non viene specificato, il valore predefinito è `On`.  
  
 `Off`  
 Facoltativo. Disabilita `Option Explicit` il controllo.  
  
## <a name="remarks"></a>Note  
 Quando `Option Explicit On` o `Option Explicit` viene visualizzato in un file, è necessario dichiarare in modo esplicito tutte le variabili utilizzando la `Dim` o `ReDim` istruzioni. Se si tenta di utilizzare un nome di variabile non dichiarato, si verifica un errore in fase di compilazione. Il `Option Explicit Off` istruzione consente la dichiarazione implicita delle variabili.  
  
 Se usato, è necessario includere l'istruzione `Option Explicit` in un file prima di tutte le altre istruzioni del codice sorgente.  
  
> [!NOTE]
>  Impostazione `Option Explicit` per `Off` non è in genere consigliabile. È possibile digitare un nome di variabile in modo errato in una o più posizioni e ciò può causare risultati imprevisti quando viene eseguito il programma.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Quando non è presente un'istruzione Option Explicit  
 Se il codice sorgente non contiene un `Option Explicit` istruzione, il **Option Explicit** impostazione di [pagina Compila, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) viene utilizzato. Se viene utilizzato il compilatore della riga di comando, il [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) viene utilizzata l'opzione del compilatore.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Per impostare Option Explicit nell'IDE  
  
1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.  
  
2.  Fare clic sulla scheda **Compila**.  
  
3.  Impostare il valore di **Option Explicit** casella.  
  
 Quando si crea un nuovo progetto, il **Option Explicit** impostazione il **compilare** scheda è impostata sul **Option Explicit** impostazione nel **VB predefinite**la finestra di dialogo. Per accedere al **VB per impostazione predefinita** della finestra di dialogo di **strumenti** menu, fare clic su **opzioni**. Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**. L'impostazione predefinita iniziale in **impostazioni predefinite di Visual Basic** è `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Per impostare Option Explicit nella riga di comando  
  
-   Includere il [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) opzione del compilatore nella **vbc** comando.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Option Explicit` istruzione per imporre la dichiarazione esplicita di tutte le variabili. Il tentativo di utilizzare una variabile dichiarata causa un errore in fase di compilazione.  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
