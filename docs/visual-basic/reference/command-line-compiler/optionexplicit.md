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
ms.openlocfilehash: 37ccd14dae0ebba2535185f2646e312d9bb70390
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266729"
---
# <a name="-optionexplicit"></a>-optionexplicit
Fa in modo che il compilatore segnali errori se le variabili non vengono dichiarate prima di essere utilizzate.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Facoltativo. Specificare `-optionexplicit+` per richiedere la dichiarazione esplicita delle variabili. L' `-optionexplicit+` opzione è l'impostazione predefinita ed è uguale a `-optionexplicit`. L' `-optionexplicit-` opzione consente la dichiarazione implicita delle variabili.  
  
## <a name="remarks"></a>Osservazioni  
 Se il file di codice sorgente contiene un' [istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), l'istruzione sostituisce `-optionexplicit` l'impostazione del compilatore da riga di comando.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>Per impostare-optionexplicit (nell'IDE di Visual Studio  
  
1. Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.
  
2. Fare clic sulla scheda **Compila**.  
  
3. Modificare il valore nella casella **Option Explicit** .  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene compilato quando `-optionexplicit-` si usa.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>Vedi anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-OptionCompare (](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-OptionStrict (](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer (](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
