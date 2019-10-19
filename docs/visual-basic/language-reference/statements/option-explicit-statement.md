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
ms.openlocfilehash: 19ff8cf1dbcdb941e38f23be4cb68d3a5e5b83a8
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582573"
---
# <a name="option-explicit-statement-visual-basic"></a>Istruzione Option Explicit (Visual Basic)
Impone la dichiarazione esplicita di tutte le variabili in un file o consente dichiarazioni implicite delle variabili.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Parti  
 `On`  
 Parametro facoltativo. Abilita il controllo `Option Explicit`. Se non si specifica `On` o `Off`, il valore predefinito è `On`.  
  
 `Off`  
 Parametro facoltativo. Disabilita il controllo `Option Explicit`.  
  
## <a name="remarks"></a>Note  
 Quando `Option Explicit On` o `Option Explicit` viene visualizzato in un file, è necessario dichiarare in modo esplicito tutte le variabili usando le istruzioni `Dim` o `ReDim`. Se si tenta di utilizzare un nome di variabile non dichiarato, si verificherà un errore in fase di compilazione. L'istruzione `Option Explicit Off` consente la dichiarazione implicita delle variabili.  
  
 Se usato, è necessario includere l'istruzione `Option Explicit` in un file prima di tutte le altre istruzioni del codice sorgente.  
  
> [!NOTE]
> Non è in genere consigliabile impostare `Option Explicit` su `Off`. È possibile digitare un nome di variabile in modo errato in una o più posizioni e ciò può causare risultati imprevisti quando viene eseguito il programma.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Quando non è presente un'istruzione Option Explicit  
 Se il codice sorgente non contiene un'istruzione `Option Explicit`, viene utilizzata l'impostazione **Option Explicit** nella [pagina compilazione, progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) . Se viene usato il compilatore da riga di comando, viene usata l'opzione del compilatore [/OptionExplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) .  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Per impostare l'opzione Explicit nell'IDE  
  
1. Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.  
  
2. Fare clic sulla scheda **Compila**.  
  
3. Impostare il valore nella casella **Option Explicit** .  
  
 Quando si crea un nuovo progetto, l'impostazione **Option Explicit** nella scheda **Compila** viene impostata sull'impostazione **Option Explicit** nella finestra di dialogo **impostazioni predefinite di Visual Basic** . Per accedere alla finestra di dialogo **impostazioni predefinite di Visual Basic** , scegliere **Opzioni**dal menu **strumenti** . Nella finestra di dialogo **Opzioni** espandere **Progetti e soluzioni**, quindi fare clic su **Impostazioni predefinite di Visual Basic**. L'impostazione predefinita iniziale in impostazioni **predefinite di Visual Basic** è `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Per impostare Option Explicit nella riga di comando  
  
- Includere l'opzione del compilatore [/OptionExplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) nel comando **vbc** .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l'istruzione `Option Explicit` per forzare la dichiarazione esplicita di tutte le variabili. Il tentativo di utilizzare una variabile non dichiarata genera un errore in fase di compilazione.  
  
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
