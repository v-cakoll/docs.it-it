---
title: Considerazioni su versione e aggiornamento per gli sviluppatori C#
description: L'introduzione delle nuove funzionalità del linguaggio nella libreria può influire sul codice che la usa.
ms.date: 09/19/2018
ms.openlocfilehash: 3ffe2f6fd64a391fddf28233dccb022c95851884
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399385"
---
# <a name="version-and-update-considerations-for-c-developers"></a>Considerazioni su versione e aggiornamento per gli sviluppatori C#

La compatibilità è un obiettivo molto importante quando vengono aggiunte nuove funzionalità al linguaggio C#. Nella quasi totalità dei casi, il codice esistente può essere ricompilato con una nuova versione del compilatore senza alcun problema.

Può essere necessaria maggiore attenzione quando si adottano le nuove funzionalità del linguaggio in una libreria. Si supponga di creare una nuova libreria con le funzionalità disponibili nella versione più recente e di dover verificare che le app create con le versioni precedenti del compilatore siano in grado di usarla. In un altro caso, potrebbe essere necessario aggiornare una libreria esistente quando molti utenti non hanno ancora eseguito l'aggiornamento delle versioni. Quando si prendono decisioni relative all'adozione di nuove funzionalità, è necessario tenere presenti due tipi di compatibilità: la compatibilità a livello binario e la compatibilità a livello di codice sorgente.

## <a name="binary-compatible-changes"></a>Modifiche compatibili a livello binario

Le modifiche apportate a una libreria sono **compatibili a livello binario** quando la libreria aggiornata può essere usata senza ricompilare le applicazioni e le librerie che la usano. Gli assembly dipendenti non devono essere ricompilati, né sono necessarie modifiche al codice sorgente. Le modifiche compatibili a livello binario sono anche compatibili a livello di codice sorgente.

## <a name="source-compatible-changes"></a>Modifiche compatibili a livello di codice sorgente

Le modifiche apportate a una libreria sono **compatibili a livello di codice sorgente** quando le applicazioni e le librerie che usano la libreria non richiedono modifiche al codice sorgente, ma l'origine deve essere ricompilata con la nuova versione per garantirne il corretto funzionamento.

## <a name="incompatible-changes"></a>Modifiche incompatibili

Se una modifica non è **compatibile a livello di codice sorgente** né **compatibile a livello binario**, sono necessarie sia modifiche al codice sorgente che la ricompilazione nelle applicazioni e librerie dipendenti.

## <a name="evaluate-your-library"></a>Valutare la libreria

Questi concetti relativi alla compatibilità interessano le dichiarazioni pubbliche e protette per la libreria, non la relativa implementazione interna. Internamente, l'adozione delle nuove funzionalità è sempre **compatibile a livello binario**.  

Le modifiche **compatibili a livello binario ** forniscono una nuova sintassi che genera lo stesso codice compilato per le dichiarazioni pubbliche della sintassi precedente. Ad esempio, la modifica di un metodo in un membro con corpo di espressione è una **modifica compatibile a livello binario**:

Codice originale:

```csharp
public double CalculateSquare(double value)
{
    return value * value;
}
```

Nuovo codice:

```csharp
public double CalculateSquare(double value) => value * value;
```

Le modifiche **compatibili a livello di codice sorgente** introducono una sintassi che modifica il codice compilato per un membro pubblico, ma in modo compatibile con i siti di chiamata esistenti. Ad esempio, la modifica di una firma di un metodo da un parametro per valore a un parametro `in` per riferimento è compatibile a livello di codice sorgente, ma non a livello binario:

Codice originale:

```csharp
public double CalculateSquare(double value) => value * value;
```

Nuovo codice:

```csharp
public double CalculateSquare(in double value) => value * value;
```

Negli articoli sulle [novità](index.md) è specificato se l'introduzione di una funzionalità che influisce sulle dichiarazioni pubbliche è compatibile a livello di codice sorgente o a livello binario.
