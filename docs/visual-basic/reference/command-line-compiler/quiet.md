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
ms.openlocfilehash: 6e773c60469e8426956c92a5aa377741ba5af4d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005286"
---
# <a name="-quiet"></a>-quiet

Impedisce al compilatore di visualizzare codice per avvisi ed errori relativi alla sintassi.

## <a name="syntax"></a>Sintassi

```console
-quiet
```

## <a name="remarks"></a>Osservazioni

Per impostazione predefinita, l'opzione `-quiet` non è attiva. Quando il compilatore segnala un errore o un avviso correlato alla sintassi, restituisce anche la riga dal codice sorgente. Per le applicazioni che analizzano l'output del compilatore, potrebbe essere più pratico per il compilatore restituire solo il testo della diagnostica.

Nell'esempio seguente viene `Module1` restituito un errore che include il codice sorgente quando viene compilato `-quiet`senza.

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

Compilato con `-quiet`, il compilatore restituisce solo quanto segue:

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> L' `-quiet` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.

## <a name="example"></a>Esempio

Il codice seguente compila `T2.vb` e non Visualizza il codice per la diagnostica del compilatore correlato alla sintassi:

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a>Vedi anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
