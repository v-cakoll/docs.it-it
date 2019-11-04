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
ms.openlocfilehash: 7312c59cdcddfdbda39a4a9f05788b6a021f9b75
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459595"
---
# <a name="xcode-intrinsic-xaml-type"></a>Tipo XAML intrinseco x:Code
Consente di posizionare il codice in una produzione XAML. Tale codice può essere compilato da qualsiasi implementazione del processore XAML che compila XAML o lasciata nell'ambiente di produzione XAML per utilizzi successivi, ad esempio l'interpretazione da parte di un Runtime.  
  
## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto  
  
```xaml  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a>Note  
 Il codice all'interno dell'elemento `x:Code` direttiva XAML viene ancora interpretato nello spazio dei nomi XML generale e negli spazi dei nomi XAML forniti. Pertanto, in genere è necessario racchiudere il codice usato per `x:Code` all'interno di un segmento di `CDATA`.  
  
 `x:Code` non è consentito per tutti i meccanismi di distribuzione possibili di una produzione XAML. In Framework specifici, ad esempio WPF, è necessario compilare il codice. In altri Framework, `x:Code` utilizzo potrebbe essere in genere non consentito.  
  
 Per i Framework che consentono il contenuto `x:Code` gestito, il compilatore di linguaggio corretto da usare per `x:Code` contenuto è determinato dalle impostazioni e dalle destinazioni del progetto contenitore usato per compilare l'applicazione.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF  
 Il codice dichiarato all'interno `x:Code` per WPF presenta diverse limitazioni rilevanti:  
  
- L'elemento `x:Code` direttiva deve essere un elemento figlio immediato dell'elemento radice della produzione XAML.  
  
- è necessario fornire la [direttiva x:Class](x-class-directive.md) sull'elemento radice padre.  
  
- Il codice inserito in `x:Code` verrà gestito dalla compilazione affinché si trovi nell'ambito della classe parziale che è già stata creata per la pagina XAML. Pertanto tutto il codice definito deve essere membro o variabili della classe parziale.  
  
- Non è possibile definire classi aggiuntive, tranne annidando una classe all'interno della classe parziale (l'annidamento è consentito, ma non è tipico perché in XAML non è possibile fare riferimento alle classi annidate). Non è possibile definire o aggiungere spazi dei nomi CLR diversi dallo spazio dei nomi usato per la classe parziale esistente.  
  
- I riferimenti alle entità di codice all'esterno dello spazio dei nomi CLR della classe parziale devono essere tutti completi. Se i membri dichiarati sono override dei membri della classe parziale sottoponibili a override, è necessario specificarli con la parola chiave di override specifica della lingua. Se i membri dichiarati in `x:Code` ambito sono in conflitto con i membri della classe parziale creata da XAML, in modo che il compilatore segnali il conflitto, il file XAML non può essere compilato o caricato.  
  
## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](x-class-directive.md)
- [Code-behind e XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Cenni preliminari su XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
