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
ms.openlocfilehash: c027964d185d7f69c0a56a4386bedc2d8f9d2eac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912342"
---
# <a name="option-explicit-statement-visual-basic"></a>Istruzione Option Explicit (Visual Basic)
Impone la dichiarazione esplicita di tutte le variabili in un file o consente dichiarazioni implicite delle variabili.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Parti  
 `On`  
 facoltativo. Consente `Option Explicit` il controllo. Se `On` `On`o `Off` non è specificato, il valore predefinito è.  
  
 `Off`  
 facoltativo. Disabilita `Option Explicit` il controllo.  
  
## <a name="remarks"></a>Note  
 Quando `Option Explicit On` `Dim` `ReDim` o `Option Explicit` viene visualizzato in un file, è necessario dichiarare in modo esplicito tutte le variabili usando le istruzioni o. Se si tenta di utilizzare un nome di variabile non dichiarato, si verificherà un errore in fase di compilazione. L' `Option Explicit Off` istruzione consente la dichiarazione implicita delle variabili.  
  
 Se usato, è necessario includere l'istruzione `Option Explicit` in un file prima di tutte le altre istruzioni del codice sorgente.  
  
> [!NOTE]
> Non `Option Explicit` è `Off` in genere consigliabile impostare su. È possibile digitare un nome di variabile in modo errato in una o più posizioni e ciò può causare risultati imprevisti quando viene eseguito il programma.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Quando non è presente un'istruzione Option Explicit  
 Se il codice sorgente non contiene un' `Option Explicit` istruzione, viene utilizzata l'impostazione **Option Explicit** nella [pagina compilazione, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) . Se viene usato il compilatore da riga di comando, viene usata l'opzione del compilatore [/OptionExplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) .  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Per impostare l'opzione Explicit nell'IDE  
  
1. Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.  
  
2. Fare clic sulla scheda **Compila**.  
  
3. Impostare il valore nella casella **Option Explicit** .  
  
 Quando si crea un nuovo progetto, l'impostazione **Option Explicit** nella scheda **Compila** viene impostata sull'impostazione **Option Explicit** nella finestra di dialogo **impostazioni predefinite di Visual Basic** . Per accedere alla finestra di dialogo **impostazioni predefinite di Visual Basic** , scegliere **Opzioni**dal menu **strumenti** . Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**. L'impostazione predefinita iniziale in impostazioni **predefinite di Visual Basic** è `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Per impostare Option Explicit nella riga di comando  
  
- Includere l'opzione del compilatore [/OptionExplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) nel comando **vbc** .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata `Option Explicit` l'istruzione per forzare la dichiarazione esplicita di tutte le variabili. Il tentativo di utilizzare una variabile non dichiarata genera un errore in fase di compilazione.  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
