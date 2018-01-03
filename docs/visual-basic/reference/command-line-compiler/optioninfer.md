---
title: /optioninfer
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2df7fa743e72d12dcef1aa9be5ea43d24ef43cee
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="optioninfer"></a>/optioninfer
Consente di usare l'inferenza del tipo di variabile locale nelle dichiarazioni di variabile.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/optioninfer[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`+` &#124; `-`|Facoltativo. Specificare `/optioninfer+` per abilitare l'inferenza del tipo di variabile locale o `/optioninfer-` per bloccarla. L'opzione `/optioninfer`, senza alcun valore specificato, equivale a `/optioninfer+`. Il valore predefinito, quando l'opzione `/optioninfer` non è presente, è anche `/optioninfer+`. Il valore predefinito viene impostato nel file di risposta Vbc.rsp.|  
  
> [!NOTE]
>  È possibile usare l'opzione `/noconfig` per mantenere le impostazioni predefinite interne del compilatore anziché quelle specificate in vbc.rsp. Il valore predefinito del compilatore per questa opzione è `/optioninfer-`.  
  
## <a name="remarks"></a>Note  
 Se il file di codice sorgente contiene un [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md), l'istruzione esegue l'override di `/optioninfer` impostazione del compilatore da riga di comando.  
  
### <a name="to-set-optioninfer-in-the-visual-studio-ide"></a>Per impostare /optioninfer nell'IDE di Visual Studio  
  
1.  Selezionare un progetto in **Esplora**. Scegliere **Proprietà** dal menu **Progetto**.  
  
2.  Nel **compilare** scheda, modificare il valore di **Option infer** casella.  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `test.vb` con l'inferenza del tipo locale abilitata.  
  
```  
vbc /optioninfer+ test.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Istruzione Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)  
 [Pagina Compilazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [Compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
