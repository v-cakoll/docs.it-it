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
ms.openlocfilehash: c42dd74ea0dc01b8ae7ffb7eb04737a9784625a9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841459"
---
# <a name="option-explicit-statement-visual-basic"></a>Istruzione Option Explicit (Visual Basic)
Forza la dichiarazione esplicita di tutte le variabili in un file o è consentito dichiarare implicite delle variabili.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Parti  
 `On`  
 Facoltativo. Abilita `Option Explicit` controllo. Se `On` oppure `Off` non viene specificato, il valore predefinito è `On`.  
  
 `Off`  
 Facoltativo. Disabilita `Option Explicit` controllo.  
  
## <a name="remarks"></a>Note  
 Quando `Option Explicit On` oppure `Option Explicit` viene visualizzato in un file, è necessario dichiarare tutte le variabili in modo esplicito tramite il `Dim` o `ReDim` istruzioni. Se si prova a usare un nome di variabile non dichiarato, si verifica un errore in fase di compilazione. Il `Option Explicit Off` istruzione consente la dichiarazione implicita delle variabili.  
  
 Se usato, è necessario includere l'istruzione `Option Explicit` in un file prima di tutte le altre istruzioni del codice sorgente.  
  
> [!NOTE]
>  L'impostazione `Option Explicit` a `Off` non è in genere una buona norma. È possibile digitare un nome di variabile in modo errato in una o più posizioni e ciò può causare risultati imprevisti quando viene eseguito il programma.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Quando non è presente un'istruzione Option Explicit  
 Se il codice sorgente non contiene un `Option Explicit` istruzione, il **Option Explicit** impostazione il [pagina compilazione, creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) viene usato. Se viene utilizzato il compilatore della riga di comando, il [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) viene utilizzata l'opzione del compilatore.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Per impostare Option Explicit nell'IDE  
  
1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.  
  
2.  Fare clic sulla scheda **Compila**.  
  
3.  Impostare il valore di **Option Explicit** casella.  
  
 Quando si crea un nuovo progetto, il **Option Explicit** impostazione nel **compilare** scheda è impostata sul **Option Explicit** impostazione nel **VB valore predefinito è**finestra di dialogo. Per l'accesso di **valore predefinito è VB** finestra di dialogo il **strumenti** dal menu fare clic su **opzioni**. Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**. L'impostazione predefinita iniziale in **le impostazioni predefinite di Visual Basic** è `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Per impostare Option Explicit nella riga di comando  
  
-   Includere il [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) opzione del compilatore nella **vbc** comando.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Option Explicit` imporre la dichiarazione esplicita di tutte le variabili dell'istruzione. Tentativo di utilizzare una varaibile causa un errore in fase di compilazione.  
  
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
