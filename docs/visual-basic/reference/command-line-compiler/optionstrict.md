---
title: -optionstrict
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2ff7d13fcb3e224ee76cdb42f3974a4eddb042f5
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="-optionstrict"></a>-optionstrict
Applica la semantica dei tipi rigorosa per limitare le conversioni implicite.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Facoltativo. Il `-optionstrict+` limita l'opzione di conversione implicita del tipo. Il valore predefinito per questa opzione è `-optionstrict-`. Il `-optionstrict+` opzione equivale `-optionstrict`. È possibile utilizzare entrambe le opzioni per la semantica dei tipi permissiva.  
  
 `custom`  
 Obbligatorio. Avvisa quando non viene rispettata la semantica del linguaggio rigorosa.  
  
## <a name="remarks"></a>Note  
 Quando `-optionstrict+` è in effetti, solo le conversioni di tipo widening possono essere eseguite in modo implicito. Conversioni di tipi, ad esempio l'assegnazione di narrowing implicite un `Decimal` tipo di oggetto a un oggetto di tipo integer, vengono segnalati come errori.  
  
 Per generare avvisi per conversioni implicite verso un tipo, utilizzare `-optionstrict:custom`. Utilizzare `-nowarn:numberlist` per ignorare determinati avvisi e `-warnaserror:numberlist` per considerare determinati avvisi come errori.  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a>Per impostare - optionstrict nell'IDE di Visual Studio  
  
1.  Selezionare un progetto in **Esplora soluzioni**. Nel **Project** menu, fare clic su **proprietà.**   
  
2.  Fare clic sulla scheda **Compila**.  
  
3.  Modificare il valore di **Option Strict** casella.  
  
### <a name="to-set--optionstrict-programmatically"></a>Per impostare a livello di programmazione - optionstrict  
  
-   Vedere [Option Strict (istruzione)](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `Test.vb` utilizzando la semantica dei tipi rigorosa.  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)  
 [-warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
