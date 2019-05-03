---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: a22773e2e37eb60ab6f1e88305266f41764311e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788843"
---
# <a name="-quiet"></a>-quiet

Impedisce al compilatore di visualizzare codice per avvisi ed errori relativi alla sintassi.

## <a name="syntax"></a>Sintassi

```
-quiet
```

## <a name="remarks"></a>Note

Per impostazione predefinita, l'opzione `-quiet` non è attiva. Quando il compilatore segnala un errore di sintassi relativa o avviso, viene visualizzata anche la riga di codice sorgente. Per le applicazioni che analizzare l'output del compilatore, potrebbe essere più utile per il compilatore di generare solo il testo della diagnostica.

Nell'esempio riportato di seguito `Module1` genera un errore che include il codice sorgente quando viene compilato senza `-quiet`.

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

Output:

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

Compilato con `-quiet`, il compilatore genera solo gli elementi seguenti:

```
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> Il `-quiet` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.

## <a name="example"></a>Esempio

Il codice seguente Compila `T2.vb` non visualizzare il codice per la diagnostica del compilatore relativi alla sintassi:

```
vbc -quiet t2.vb
```

## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
