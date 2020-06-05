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
ms.openlocfilehash: f894ed6a778e026ffd3976a63fe3b677eb6a9557
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400526"
---
# <a name="-quiet"></a>-quiet

Impedisce al compilatore di visualizzare codice per avvisi ed errori relativi alla sintassi.

## <a name="syntax"></a>Sintassi

```console
-quiet
```

## <a name="remarks"></a>Osservazioni

Per impostazione predefinita, l'opzione `-quiet` non è attiva. Quando il compilatore segnala un errore o un avviso correlato alla sintassi, restituisce anche la riga dal codice sorgente. Per le applicazioni che analizzano l'output del compilatore, potrebbe essere più pratico per il compilatore restituire solo il testo della diagnostica.

Nell'esempio seguente viene `Module1` restituito un errore che include il codice sorgente quando viene compilato senza `-quiet` .

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

Compilato con `-quiet` , il compilatore restituisce solo quanto segue:

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

## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
