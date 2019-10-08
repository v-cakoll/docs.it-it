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
ms.openlocfilehash: 6d281fe07754f0471f8d6c0e31cf3ea890060504
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005345"
---
# <a name="-optionstrict"></a>-optionstrict
Applica una semantica dei tipi rigorosa per limitare le conversioni implicite dei tipi.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 facoltativo. L'opzione `-optionstrict+` limita la conversione implicita di tipi. Il valore predefinito per questa opzione è `-optionstrict-`. L'opzione `-optionstrict+` corrisponde a `-optionstrict`. È possibile utilizzare entrambi per la semantica di tipo permissivo.  
  
 `custom`  
 Obbligatorio. Avvisa quando la semantica del linguaggio strict non viene rispettata.  
  
## <a name="remarks"></a>Note  
 Quando `-optionstrict+` è attivo, è possibile rendere implicite solo le conversioni verso un tipo più ampio. Le conversioni implicite di tipi più restrittivi, ad esempio l'assegnazione di un oggetto di tipo `Decimal` a un oggetto di tipo Integer, vengono segnalate come errori.  
  
 Per generare avvisi per le conversioni implicite di tipi più restrittivi, utilizzare `-optionstrict:custom`. Utilizzare `-nowarn:numberlist` per ignorare determinati avvisi e `-warnaserror:numberlist` per considerare determinati avvisi come errori.  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a>Per impostare-optionstrict (nell'IDE di Visual Studio  
  
1. Selezionare un progetto in **Esplora soluzioni**. Scegliere Proprietà dal menu **progetto** **.**   
  
2. Fare clic sulla scheda **Compila**.  
  
3. Modificare il valore nella casella **Option Strict** .  
  
### <a name="to-set--optionstrict-programmatically"></a>Per impostare-optionstrict (a livello di codice  
  
- Vedere [istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `Test.vb` usando la semantica di tipo strict.  
  
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
- [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
