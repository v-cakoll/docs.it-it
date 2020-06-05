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
ms.openlocfilehash: 3dd12971a082869c32b6292ed45e2014b8b0e2c0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400539"
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
Facoltativa. L' `-optionstrict+` opzione limita la conversione implicita di tipi. Il valore predefinito per questa opzione è `-optionstrict-` . L' `-optionstrict+` opzione è uguale a `-optionstrict` . È possibile utilizzare entrambi per la semantica di tipo permissivo.

`custom`  
Obbligatorio. Avvisa quando la semantica del linguaggio strict non viene rispettata.

## <a name="remarks"></a>Commenti

Quando `-optionstrict+` è attivo, è possibile effettuare in modo implicito solo le conversioni verso un tipo più ampio. Le conversioni implicite di tipi più piccoli, ad esempio l'assegnazione `Decimal` di un oggetto tipo a un oggetto di tipo Integer, vengono segnalate come errori.

Per generare avvisi per le conversioni implicite di tipi più restrittivi, usare `-optionstrict:custom` . Utilizzare `-nowarn:numberlist` per ignorare determinati avvisi e `-warnaserror:numberlist` considerare determinati avvisi come errori.

### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a>Per impostare-optionstrict (nell'IDE di Visual Studio

1. Selezionare un progetto in **Esplora soluzioni**. Scegliere Proprietà dal menu **progetto** **.**

2. Fare clic sulla scheda **Compila**.

3. Modificare il valore nella casella **Option Strict** .

### <a name="to-set--optionstrict-programmatically"></a>Per impostare-optionstrict (a livello di codice

Vedere [istruzione Option Strict](../../language-reference/statements/option-strict-statement.md).

## <a name="example"></a>Esempio

Il codice seguente viene compilato `Test.vb` usando la semantica di tipo strict.

```console
vbc -optionstrict+ test.vb
```

## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [-optioncompare](optioncompare.md)
- [-optionexplicit](optionexplicit.md)
- [-optioninfer](optioninfer.md)
- [-nowarn](nowarn.md)
- [-warnaserror (Visual Basic)](warnaserror.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
- [Option Strict Statement](../../language-reference/statements/option-strict-statement.md)
- [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
