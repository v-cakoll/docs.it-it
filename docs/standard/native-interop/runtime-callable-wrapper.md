---
title: Runtime Callable Wrapper
ms.date: 03/30/2017
helpviewer_keywords:
- COM interop, COM wrappers
- RCW
- COM wrappers
- runtime callable wrappers
- interoperation with unmanaged code, COM wrappers
ms.assetid: 7e542583-1e31-4e10-b523-8cf2f29cb4a4
ms.openlocfilehash: 0b448379fba965060fdf3bf067e65374f40d1fc2
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156010"
---
# <a name="runtime-callable-wrapper"></a>Runtime Callable Wrapper
Common Language Runtime espone gli oggetti COM tramite un proxy denominato Runtime Callable Wrapper (RCW). Benché l'RCW appaia ai client .NET come un normale oggetto, la sua funzione principale consiste nell'effettuare il marshalling tra un client .NET e un oggetto COM.  
  
 Il runtime crea esattamente un RCW per ciascun oggetto COM, indipendentemente dal numero di riferimenti all'oggetto. Il runtime mantiene un solo RCW a processo per ciascun oggetto.  Se si crea un RCW in un apartment o dominio applicazione e si passa quindi un riferimento a un altro apartment o dominio applicazione, verrà usato un proxy al primo oggetto.  Come illustrato nella figura che segue, un numero qualsiasi di client gestiti può stabilire un riferimento agli oggetti COM che espongono le interfacce INew e INewer.  

La figura seguente illustra il processo per accedere a oggetti COM tramite Runtime Callable Wrapper:

 ![Processo per accedere a oggetti COM tramite RCW.](./media/runtime-callable-wrapper/runtime-callable-wrapper.gif)  

 Usando i metadati derivati da una libreria dei tipi, il runtime crea sia l'oggetto COM che si sta chiamando che il relativo wrapper. Ogni RCW mantiene una cache dei puntatori a interfaccia impostati sull'oggetto COM di cui effettua il wrapping e rilascia i riferimenti all'oggetto COM quando l'RCW non è più necessario. Il runtime esegue la procedura di Garbage Collection sull'RCW.  
  
 Tra le altre attività, l'RCW effettua il marshalling dei dati trasferiti tra il codice gestito e quello non gestito, per conto dell'oggetto di cui effettua il wrapping. In particolare, l'RCW effettua il marshalling degli argomenti e dei valori restituiti dei metodi ogni volta che il client e il server adottano rappresentazioni diverse dei dati scambiati.  
  
 Il wrapper standard applica le regole di marshalling incorporate. Quando ad esempio un client .NET passa come parte di un argomento un tipo String a un oggetto gestito, il wrapper converte la stringa in un tipo BSTR. Nel caso in cui l'oggetto COM dovesse restituire un valore di tipo BSTR, il relativo chiamante gestito riceverebbe una stringa. Sia il client che il server inviano e ricevono dati rispettivamente noti. Gli altri tipi non richiedono alcuna conversione. Un wrapper standard, ad esempio, trasferirà sempre un intero di 4 byte tra il codice gestito e quello non gestito senza operare alcuna conversione di tipo.  
  
## <a name="marshaling-selected-interfaces"></a>Interfacce sottoposte a marshalling  
 L'obiettivo principale di un oggetto [Runtime Callable Wrapper](runtime-callable-wrapper.md) (RCW) è quello di nascondere le differenze tra i modelli di programmazione gestiti e non gestiti. Per semplificare la transizione, l'RCW usa interfacce COM selezionate senza esporle al client .NET, come illustrato nella figura che segue.

 L'immagine seguente illustra le interfacce COM e Runtime Callable Wrapper:
  
 ![Screenshot di Runtime Callable Wrapper con interfacce.](./media/runtime-callable-wrapper/runtime-callable-wrapper-interfaces.gif)  
  
 Quando viene creato come oggetto ad associazione anticipata, l'RCW è specifico del tipo. Esso implementa le interfacce implementate dall'oggetto COM ed espone i metodi, le proprietà e gli eventi delle interfacce dell'oggetto. Nella figura l'oggetto RCW espone l'interfaccia INew, ma utilizza le interfacce **IUnknown** e **IDispatch**. L'RCW espone inoltre al client .NET tutti i membri dell'interfaccia INew.  
  
 L'RCW usa le interfacce elencate nella tabella che segue, che sono esposte dall'oggetto di cui effettua il wrapping.  
  
|Interfaccia|Descrizione|  
|---------------|-----------------|  
|**IDispatch**|Per l'associazione tardiva a oggetti COM tramite reflection.|  
|**IErrorInfo**|Fornisce una descrizione testuale dell'errore, la relativa origine, un file della Guida, un contesto della Guida e il GUID dell'interfaccia che ha definito l'errore (sempre **GUID_NULL** per le classi .NET).|  
|**IProvideClassInfo**|Se l'oggetto COM di cui si esegue il wrapping implementa **IProvideClassInfo**, l'oggetto RCW estrarrà le informazioni sul tipo da questa interfaccia per definire meglio l'identità del tipo.|  
|**IUnknown**|Per l'identità del tipo, la coercizione dei tipi e la gestione della durata:<br /><br /> - Identità degli oggetti<br />     Il runtime distingue tra gli oggetti COM confrontando il valore dell'interfaccia **IUnknown** di ciascun oggetto.<br />- Coercizione dei tipi<br />     L'oggetto RCW riconosce l'individuazione dei tipi dinamica eseguita dal metodo **QueryInterface**.<br />- Gestione del ciclo di vita<br />     Usando il metodo **QueryInterface**, l'oggetto RCW ottiene e mantiene un riferimento a un oggetto non gestito fino a quando il runtime non esegue una procedura di Garbage Collection sul wrapper, rilasciando l'oggetto non gestito.|  
  
 RCW usa facoltativamente le interfacce elencate nella tabella che segue, che sono esposte dall'oggetto di cui effettua il wrapping.  
  
|Interfaccia|Descrizione|  
|---------------|-----------------|  
|**IConnectionPoint** e **IConnectionPointContainer**|Talvolta l'RCW usa le interfacce elencate nella tabella che segue, che sono esposte dall'oggetto di cui effettua il wrapping.|  
|**IDispatchEx** (solo .NET Framework) |Se la classe implementa **IDispatchEx**, l'oggetto RCW implementa **IExpando**. L'interfaccia **IDispatchEx** è un'estensione dell'interfaccia **IDispatch** che, diversamente da **IDispatch**, consente l'enumerazione, l'aggiunta, l'eliminazione e la chiamata dei membri con distinzione tra maiuscole e minuscole.|  
|**IEnumVARIANT**|Consente di trattare come raccolte i tipi COM che supportano l'enumerazione.|  
  
## <a name="see-also"></a>Vedi anche

- [Wrapper COM](com-wrappers.md)
- [COM Callable Wrapper](com-callable-wrapper.md)
- [Riepilogo della conversione da libreria dei tipi ad assembly](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))
- [Importazione di una libreria dei tipi come assembly](../../framework/interop/importing-a-type-library-as-an-assembly.md)
