---
title: Tipo di dati Date
ms.date: 07/20/2015
f1_keywords:
- vb.Date
helpviewer_keywords:
- Date data type
- dates [Visual Basic], Visual Basic data types
- times [Visual Basic], Date data type
- Date literals [Visual Basic]
- data values [Visual Basic]
- times [Visual Basic], Visual Basic data types
- dates [Visual Basic], Date data type
- data types [Visual Basic], assigning
- literals [Visual Basic], Date
- '# specifier for Date literals'
ms.assetid: d9edf5b0-e85e-438b-a1cf-1f321e7c831b
ms.openlocfilehash: 46c25e14db56d4cc3c6d59ec7649b37c35676e2e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387426"
---
# <a name="date-data-type-visual-basic"></a>Tipo di dati Date (Visual Basic)

Contiene valori a 64 bit (8 byte) conformi alle specifiche IEEE che rappresentano le date comprese tra l'1 gennaio dell'anno 0001 e il 31 dicembre dell'anno 9999 e le ore comprese tra le 00.00.00 (mezzanotte) e le 23.59.59.9999999. Ogni incremento rappresenta 100 nanosecondi di tempo trascorso dall'inizio del 1° gennaio dell'anno 1 del calendario gregoriano. Il valore massimo rappresenta 100 nanosecondi prima dell'inizio del 1° gennaio dell'anno 10000.

## <a name="remarks"></a>Commenti

Usare il tipo di dati `Date` per contenere valori di data, di ora o entrambi.

Il valore predefinito di `Date` è 00.00.00 (mezzanotte) del 1° gennaio 0001.

È possibile ottenere la data e l'ora corrente dalla classe <xref:Microsoft.VisualBasic.DateAndTime>.

## <a name="format-requirements"></a>Requisiti di formato

È necessario racchiudere un valore letterale `Date` tra simboli di cancelletto (`# #`). Il valore della data deve essere specificato nel formato M/g/aaaa, ad esempio `#5/31/1993#`, oppure aaaa-MM-gg, ad esempio `#1993-5-31#`. Quando si specifica prima l'anno, è possibile usare le barre.  Questo requisito è indipendente dalle impostazioni locali usate e dalle impostazioni relative al formato di data e ora del computer.

Il motivo di questa limitazione è che il significato del codice non deve mai cambiare a seconda delle impostazioni locali con cui l'applicazione viene eseguita. Si supponga di impostare come hardcoded il valore letterale `Date``#3/4/1998#` per rappresentare la data del 4 marzo 1998. Se nelle impostazioni locali è definito il formato mm/gg/aaaa, la compilazione di 3/4/1998 viene eseguita nel modo desiderato. Si supponga, tuttavia, di distribuire l'applicazione in molti paesi o aree geografiche. Se nelle impostazioni locali è definito il formato gg/mm/aaaa, il valore letterale hardcoded verrà compilato come 3 aprile 1998. Se invece è definito il formato aaaa/mm/gg, il valore letterale non sarà valido (1998 aprile 0003) e verrà generato un errore del compilatore.

## <a name="workarounds"></a>Soluzioni alternative

Per convertire un valore letterale `Date` nel formato delle impostazioni locali in uso o in un formato personalizzato, fornire il valore letterale alla funzione <xref:Microsoft.VisualBasic.Strings.Format%2A>, specificando un formato di data predefinito o definito dall'utente. L'esempio seguente illustra questa operazione.

```vb
MsgBox("The formatted date is " & Format(#5/31/1993#, "dddd, d MMM yyyy"))
```

In alternativa, si può usare uno dei costruttori di overload della struttura <xref:System.DateTime> per assemblare un valore di data e ora. L'esempio seguente crea un valore per rappresentare le ore 12.14 del 31 maggio 1993.

```vb
Dim dateInMay As New System.DateTime(1993, 5, 31, 12, 14, 0)
```

## <a name="hour-format"></a>Formato dell'ora

È possibile specificare il valore dell'ora nel formato 12 o 24 ore, ad esempio `#1:15:30 PM#` o `#13:15:30#`.  Tuttavia, se non si specificano i minuti o i secondi, è necessario indicare AM o PM.

## <a name="date-and-time-defaults"></a>Valori predefiniti di data e ora

Se non si include una data in un valore letterale di data/ora, Visual Basic imposta la parte del valore relativa alla data sul 1° gennaio 0001. Se non si include un'ora in un valore letterale di data/ora, Visual Basic imposta la parte del valore relativa all'ora sull'inizio della giornata, ossia mezzanotte (00.00.00).

## <a name="type-conversions"></a>Conversione di tipi

Se un valore `Date` viene convertito nel tipo `String`, Visual Basic esegue il rendering della data e dell'ora rispettivamente in base al formato breve e al formato 12 o 24 ore specificati nelle impostazioni locali di runtime.

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Considerazioni sull'interoperabilità.** Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di data/ora in altri ambienti non sono compatibili con il tipo `Date` di Visual Basic. Se si passa un argomento di data/ora a un componente di questo tipo, nel nuovo codice Visual Basic è necessario dichiararlo come `Double` anziché come `Date` e usare i metodi di conversione <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> e <xref:System.DateTime.ToOADate%2A?displayProperty=nameWithType>.

- **Digitare i caratteri.** `Date`non ha un carattere di tipo letterale o un carattere di tipo identificatore. Il compilatore considera tuttavia i valori letterali racchiusi tra simboli del cancelletto (`# #`) come valori `Date`.

- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.DateTime?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

Una variabile o una costante del tipo di dati `Date` contiene sia la data che l'ora. Questa condizione è illustrata nell'esempio seguente.

```vb
Dim someDateAndTime As Date = #8/13/2002 12:14 PM#
```

## <a name="see-also"></a>Vedere anche

- <xref:System.DateTime?displayProperty=nameWithType>
- [Tipi di dati](index.md)
- [Stringhe di formato di data e ora standard](../../../standard/base-types/standard-date-and-time-format-strings.md)
- [Stringhe di formato di data e ora personalizzato](../../../standard/base-types/custom-date-and-time-format-strings.md)
- [CString](../functions/type-conversion-functions.md)
- [Riepilogo della conversione](../keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
