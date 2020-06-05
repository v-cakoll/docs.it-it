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
ms.openlocfilehash: ed9adc7cddd9eb204937b9819e4eeff176821e95
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400558"
---
# <a name="-optioncompare"></a>-optioncompare

Specifica la modalità con cui vengono confrontate le stringhe.

## <a name="syntax"></a>Sintassi

```console
-optioncompare:{binary | text}
```

## <a name="remarks"></a>Osservazioni

È possibile specificare `-optioncompare` in uno dei due formati seguenti: `-optioncompare:binary` per usare i confronti di stringhe binarie e `-optioncompare:text` per usare i confronti di stringhe di testo. Per impostazione predefinita, il compilatore utilizza `-optioncompare:binary` .

In Microsoft Windows la tabella codici corrente determina l'ordinamento binario. Un ordinamento binario tipico è il seguente:

`A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

I confronti di stringhe basati su testo sono basati su un ordinamento del testo senza distinzione tra maiuscole e minuscole determinato dalle impostazioni locali del sistema. Di seguito è riportato un tipico ordinamento del testo:

`(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`

### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a>Per impostare-optioncompare (nell'IDE di Visual Studio

1. Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.

2. Fare clic sulla scheda **Compila**.

3. Modificare il valore nella casella **Option Compare** .

### <a name="to-set--optioncompare-programmatically"></a>Per impostare-optioncompare (a livello di codice

Vedere [istruzione Option Compare](../../language-reference/statements/option-compare-statement.md).

## <a name="example"></a>Esempio

Il codice seguente compila `ProjFile.vb` e usa i confronti di stringhe binarie.

```console
vbc -optioncompare:binary projFile.vb
```

## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [-optionexplicit](optionexplicit.md)
- [-optionstrict](optionstrict.md)
- [-optioninfer](optioninfer.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
- [Istruzione Option Compare](../../language-reference/statements/option-compare-statement.md)
- [Impostazioni predefinite di Visual Basic, Progetti, finestra di dialogo Opzioni](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
