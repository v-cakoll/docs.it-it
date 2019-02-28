---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 1de1b3a816739fc5f8ba1d1251b673c0b708d106
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969492"
---
# <a name="-optionexplicit"></a>-optionexplicit
Indica al compilatore di segnalare errori se le variabili non vengono dichiarate prima che vengano utilizzate.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Facoltativo. Specificare `-optionexplicit+` per richiedere la dichiarazione esplicita delle variabili. Il `-optionexplicit+` opzione è l'impostazione predefinita ed equivale a `-optionexplicit`. Il `-optionexplicit-` opzione consente la dichiarazione implicita delle variabili.  
  
## <a name="remarks"></a>Note  
 Se il file di codice sorgente contiene un' [istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), l'istruzione esegue l'override di `-optionexplicit` impostazione da riga di comando del compilatore.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>Per impostare - optionexplicit nell'IDE di Visual Studio  
  
1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.   
  
2.  Fare clic sulla scheda **Compila**.  
  
3.  Modificare il valore di **Option Explicit** casella.  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene compilato quando `-optionexplicit-` viene usato.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>Vedere anche
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
