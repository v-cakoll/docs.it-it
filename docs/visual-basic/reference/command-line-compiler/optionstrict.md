---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: e18fe451ea4a80ac959ed61b66394920f8bf177f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336083"
---
# <a name="-optionstrict"></a>-optionstrict
Applica una semantica dei tipi rigorosa per limitare le conversioni implicite.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Facoltativo. Il `-optionstrict+` limita l'opzione di conversione implicita del tipo. Il valore predefinito per questa opzione è `-optionstrict-`. Il `-optionstrict+` opzione è identico `-optionstrict`. È possibile utilizzare entrambi per la semantica di tipo permissivo.  
  
 `custom`  
 Obbligatorio. Avvisa quando non viene rispettata la semantica del linguaggio rigorosa.  
  
## <a name="remarks"></a>Note  
 Quando si `-optionstrict+` è attiva, solo le conversioni di tipo widening possono essere eseguite in modo implicito. Conversioni di tipi, ad esempio l'assegnazione di narrowing implicite un `Decimal` tipo object per un oggetto di tipo integer, vengono segnalati come errori.  
  
 Per generare avvisi per conversioni di tipo narrowing, utilizzare `-optionstrict:custom`. Uso `-nowarn:numberlist` per ignorare determinati avvisi e `-warnaserror:numberlist` particolare considerarli come errori.  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a>Per impostare - optionstrict nell'IDE di Visual Studio  
  
1. Selezionare un progetto in **Esplora soluzioni**. Nel **Project** menu, fare clic su **proprietà.**   
  
2. Fare clic sulla scheda **Compila**.  
  
3. Modificare il valore di **Option Strict** casella.  
  
### <a name="to-set--optionstrict-programmatically"></a>Per impostare a livello di codice - optionstrict  
  
-   Visualizzare [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `Test.vb` mediante la semantica di tipo strict.  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [-warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
