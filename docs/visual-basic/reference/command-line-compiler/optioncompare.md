---
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
ms.openlocfilehash: b88cba4d16c5a770a72b47868d11b16cbba6cae8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340438"
---
# <a name="-optioncompare"></a>-optioncompare
Specifica la modalità con cui vengono confrontate le stringhe.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a>Note  
 È possibile specificare `-optioncompare` in uno dei due formati: `-optioncompare:binary` usare confronti di stringhe binarie e `-optioncompare:text` usare confronti di stringhe di testo. Per impostazione predefinita, il compilatore Usa `-optioncompare:binary`.  
  
 In Microsoft Windows, la tabella codici corrente determina l'ordinamento binario. Come indicato di seguito è riportato un tipico ordinamento binario:  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 I confronti di stringhe basata su testo si basano su un ordinamento testo tra maiuscole e minuscole determinato dalle impostazioni locali del sistema. Come indicato di seguito è riportato un ordinamento testo tipico:  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a>Per impostare - optioncompare nell'IDE di Visual Studio  
  
1. Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.   
  
2. Fare clic sulla scheda **Compila**.  
  
3. Modificare il valore di **Option Compare** casella.  
  
### <a name="to-set--optioncompare-programmatically"></a>Per impostare a livello di codice - optioncompare  
  
-   Visualizzare [istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `ProjFile.vb` e confronti tra stringhe binarie.  
  
```console
vbc -optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
