---
title: -optioncompare
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 033be2ce3845ed470d56c2097b89b81d10275046
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="-optioncompare"></a>-optioncompare
Specifica la modalità con cui vengono confrontate le stringhe.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a>Note  
 È possibile specificare `-optioncompare` in uno dei due formati: `-optioncompare:binary` per utilizzare confronti tra stringhe binarie e `-optioncompare:text` per utilizzare confronti tra stringhe di testo. Per impostazione predefinita, il compilatore utilizza `-optioncompare:binary`.  
  
 In Microsoft Windows, la tabella codici corrente determina l'ordinamento binario. Un tipico ordinamento binario è il seguente:  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Confronti tra stringhe basati su testo sono in base all'ordinamento senza distinzione tra maiuscole determinato dalle impostazioni locali del sistema. Un ordinamento testo tipico è la seguente:  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a>Per impostare - optioncompare nell'IDE di Visual Studio  
  
1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.   
  
2.  Fare clic sulla scheda **Compila**.  
  
3.  Modificare il valore di **Option Compare** casella.  
  
### <a name="to-set--optioncompare-programmatically"></a>Per impostare a livello di programmazione - optioncompare  
  
-   Vedere [Option Compare (istruzione)](../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `ProjFile.vb` e confronti tra stringhe binarie.  
  
```console
vbc -optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
