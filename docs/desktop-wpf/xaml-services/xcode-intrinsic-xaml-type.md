---
title: Tipo XAML intrinseco x:Code
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 4da72ed630c1df001e3fd6c7e55f866b94c4d9b1
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071556"
---
# <a name="xcode-intrinsic-xaml-type"></a>Tipo XAML intrinseco x:Code
Consente il posizionamento del codice all'interno di una produzione XAML. Tale codice può essere compilato da qualsiasi implementazione del processore XAML che compila XAML o lasciato nella produzione XAML per usi successivi, ad esempio l'interpretazione da parte di un runtime.

## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto

```xaml
<x:Code>
   // code instructions, usually enclosed by CDATA...
</x:Code>
```

## <a name="remarks"></a>Osservazioni

Il codice `x:Code` all'interno dell'elemento della direttiva XAML viene comunque interpretato all'interno dello spazio dei nomi XML generale e degli spazi dei nomi XAML forniti. Pertanto, è in genere necessario `x:Code` racchiudere `CDATA` il codice utilizzato per l'interno di un segmento.

`x:Code`non è consentito per tutti i possibili meccanismi di distribuzione di una produzione XAML. In framework specifici (ad esempio WPFWPF) il codice deve essere compilato. In altri framework, `x:Code` l'utilizzo potrebbe essere in genere non consentito.

Per i framework `x:Code` che consentono il contenuto gestito, il compilatore di linguaggio corretto da utilizzare per `x:Code` il contenuto è determinato dalle impostazioni e dalle destinazioni del progetto contenitore utilizzato per compilare l'applicazione.

## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF

Il codice `x:Code` dichiarato all'interno di WPFWPF presenta diverse limitazioni notevoli:Code declared within within for WPF has several notable limitations:

- L'elemento `x:Code` della direttiva deve essere un elemento figlio immediato dell'elemento radice della produzione XAML.

- [X:Class Direttiva](xclass-directive.md) deve essere fornito nell'elemento radice padre.

- Il codice `x:Code` inserito all'interno verrà considerato dalla compilazione nell'ambito della classe parziale già creata per la pagina XAML. Pertanto tutto il codice definito deve essere membri o variabili di tale classe parziale.

- Non è possibile definire classi aggiuntive, se non annidando una classe all'interno della classe parziale (l'annidamento è consentito, ma non è tipico perché non è possibile fare riferimento alle classi annidate in XAML). Gli spazi dei nomi CLR diversi dallo spazio dei nomi utilizzato per la classe parziale esistente non possono essere definiti o aggiunti.

- I riferimenti alle entità di codice all'esterno dello spazio dei nomi CLR della classe parziale devono essere tutti completi. Se i membri dichiarati sono override per la classe parziale sottoponibili a override, questo deve essere specificato con la parola chiave override specifica del linguaggio. Se i `x:Code` membri dichiarati nell'ambito sono in conflitto con i membri della classe parziale creata dal codice XAML, in modo che il compilatore segnala il conflitto, il file XAML non può compilare o caricare.

## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](xclass-directive.md)
- [Code-behind e XAML in WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Panoramica di XAML (WPF)](../fundamentals/xaml.md)
