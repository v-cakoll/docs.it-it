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
ms.openlocfilehash: b004acb0c1c7d145c59a1e3a88ef7f1d405a91c6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400559"
---
# <a name="-optionexplicit"></a>-optionexplicit
Fa in modo che il compilatore segnali errori se le variabili non vengono dichiarate prima di essere utilizzate.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Facoltativa. Specificare `-optionexplicit+` per richiedere la dichiarazione esplicita delle variabili. L' `-optionexplicit+` opzione è l'impostazione predefinita ed è uguale a `-optionexplicit` . L' `-optionexplicit-` opzione consente la dichiarazione implicita delle variabili.  
  
## <a name="remarks"></a>Commenti  
 Se il file di codice sorgente contiene un' [istruzione Option Explicit](../../language-reference/statements/option-explicit-statement.md), l'istruzione sostituisce l' `-optionexplicit` impostazione del compilatore da riga di comando.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>Per impostare-optionexplicit (nell'IDE di Visual Studio  
  
1. Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.
  
2. Fare clic sulla scheda **Compila**.  
  
3. Modificare il valore nella casella **Option Explicit** .  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene compilato quando `-optionexplicit-` si usa.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [-optioncompare](optioncompare.md)
- [-optionstrict](optionstrict.md)
- [-optioninfer](optioninfer.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
- [Istruzione Option Explicit](../../language-reference/statements/option-explicit-statement.md)
- [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
