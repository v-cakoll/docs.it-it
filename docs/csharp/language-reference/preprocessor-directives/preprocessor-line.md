---
title: '#line - Riferimenti per C#'
ms.date: 07/20/2015
f1_keywords:
- '#line'
helpviewer_keywords:
- '#line directive [C#]'
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
ms.openlocfilehash: 79033fa652af62c76d54737fbf0a0b47cf3aae99
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712494"
---
# <a name="line-c-reference"></a>#line (Riferimenti per C#)

`#line` consente di modificare il numero di riga del compilatore e, facoltativamente, l'output del nome del file per gli errori e gli avvisi.

Nell'esempio seguente viene illustrata la modalità di segnalazione di due avvisi associati a numeri di riga. La direttiva `#line 200` forza l'impostazione del numero di riga successivo su 200 (anche se l'impostazione predefinita è 6) e, fino alla successiva direttiva `#line`, il nome file viene indicato come "Special". La direttiva `#line default` reimposta la numerazione predefinita delle righe, con il conteggio delle righe rinumerate dalla direttiva precedente.

```csharp
class MainClass
{
    static void Main()
    {
#line 200 "Special"
        int i;
        int j;
#line default
        char c;
        float f;
#line hidden // numbering not affected
        string s;
        double d;
    }
}
```

La compilazione produce l'output seguente:

```console
Special(200,13): warning CS0168: The variable 'i' is declared but never used
Special(201,13): warning CS0168: The variable 'j' is declared but never used
MainClass.cs(9,14): warning CS0168: The variable 'c' is declared but never used
MainClass.cs(10,15): warning CS0168: The variable 'f' is declared but never used
MainClass.cs(12,16): warning CS0168: The variable 's' is declared but never used
MainClass.cs(13,16): warning CS0168: The variable 'd' is declared but never used
```

## <a name="remarks"></a>Osservazioni

La direttiva `#line` può essere usata in un'istruzione automatizzata intermedia nel processo di compilazione. Se, ad esempio, sono state rimosse delle righe dal file del codice sorgente originale e si vuole che il compilatore generi comunque un output basato sulla numerazione originale delle righe del file, è possibile rimuovere le righe e simulare la numerazione originale tramite `#line`.

La direttiva `#line hidden` nasconde al debugger le righe successive, in modo che quando lo sviluppatore eseguirà il codice un'istruzione alla volta, verranno eseguite tutte le righe racchiuse tra una direttiva `#line hidden` e la successiva direttiva `#line` (supposto che non si tratti di un'altra direttiva `#line hidden`). Questa opzione può essere usata anche per consentire ad ASP.NET di distinguere il codice definito dall'utente da quello generato dal computer. Sebbene ASP.NET rappresenti il consumer principale di questa funzionalità, è probabile che ne usufruiscano anche altri generatori di codice sorgente.

Una direttiva `#line hidden` non influisce sui nomi di file o sui numeri di riga nella segnalazione degli errori. In questo modo, se viene rilevato un errore in un blocco nascosto, nel compilatore verrà segnalato il nome del file corrente e il numero di riga dell'errore.

La direttiva `#line filename` specifica il nome del file che si vuole venga visualizzato nell'output del compilatore. Per impostazione predefinita, viene usato il nome effettivo del file del codice sorgente. Il nome del file deve essere racchiuso tra virgolette doppie (" ") e deve essere preceduto da un numero di riga.

I file del codice sorgente possono contenere più direttive `#line`.

## <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene illustrato come il debugger ignori le righe nascoste nel codice. Durante l'esecuzione dell'esempio, verranno visualizzate tre righe di testo. Tuttavia, se si imposta un punto di interruzione, come illustrato nell'esempio, e si preme F10 per eseguire il codice un'istruzione alla volta, si noterà che la riga nascosta verrà ignorata. La stessa cosa si verifica anche se si imposta un punto di interruzione in corrispondenza della riga nascosta.

```csharp
// preprocessor_linehidden.cs
using System;
class MainClass
{
    static void Main()
    {
        Console.WriteLine("Normal line #1."); // Set break point here.
#line hidden
        Console.WriteLine("Hidden line.");
#line default
        Console.WriteLine("Normal line #2.");
    }
}
```

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Direttive per il preprocessore di C](./index.md)
