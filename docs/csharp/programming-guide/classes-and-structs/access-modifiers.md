---
title: Modificatori di accesso - Guida per programmatori C#
ms.date: 03/08/2020
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
ms.openlocfilehash: 749d53344a2518966cfa5d937069ba73dfd6be8f
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628228"
---
# <a name="access-modifiers-c-programming-guide"></a>Modificatori di accesso (Guida per programmatori C#)

Tutti i tipi e i membri dei tipi hanno un livello di accessibilità. Il livello di accessibilità controlla se possono essere usati da altro codice nell'assembly o in altri assembly. Usare i modificatori di accesso seguenti per specificare l'accessibilità di un tipo o di un membro quando lo si dichiara:

- [public](../../language-reference/keywords/public.md): il tipo o il membro può accedere a qualsiasi altro codice nello stesso assembly o in un altro assembly che vi fa riferimento.
- [privato](../../language-reference/keywords/private.md): il tipo o il membro è accessibile solo dal codice nello stesso `class` o `struct`.
- [protected](../../language-reference/keywords/protected.md): il tipo o il membro è accessibile solo dal codice nella stessa `class`o in una `class` derivata da tale `class`.
- [Internal](../../language-reference/keywords/internal.md): il tipo o il membro è accessibile da qualsiasi codice nello stesso assembly, ma non da un altro assembly.
- [interno protetto](../../language-reference/keywords/protected-internal.md): il tipo o il membro è accessibile da qualsiasi codice nell'assembly in cui è dichiarato o dall'interno di una `class` derivata in un altro assembly.
- [privato protetto](../../language-reference/keywords/private-protected.md): il tipo o il membro è accessibile solo all'interno dell'assembly dichiarante, dal codice nello stesso `class` o in un tipo derivato da tale `class`.

L'esempio seguente illustra come specificare i modificatori di accesso in un tipo e in un membro:

[!code-csharp[PublicAccess](~/samples/snippets/csharp/objectoriented/accessmodifiers.cs#PublicAccess)]

Non tutti i modificatori di accesso sono validi per tutti i tipi o i membri in tutti i contesti. In alcuni casi, l'accessibilità di un membro del tipo è vincolata dall'accessibilità del tipo che lo contiene.

## <a name="class-and-struct-accessibility"></a>Accessibilità di classi e struct  

Le classi e gli struct dichiarati direttamente all'interno di uno spazio dei nomi (in altre parole, che non sono annidati all'interno di altre classi o struct) possono essere `public` o `internal`. `Internal` è l'impostazione predefinita se non viene specificato alcun modificatore di accesso.  

I membri struct, incluse le classi e gli struct annidati, possono essere dichiarati `public`, `internal`o `private`. I membri della classe, incluse le classi e gli struct annidati, possono essere `public`, `protected internal`, `protected`, `internal`, `private protected`o `private`. I membri della classe e dello struct, incluse le classi e gli struct annidati, hanno `private` l'accesso per impostazione predefinita. I tipi annidati privati non sono accessibili dall'esterno del tipo che lo contiene.

Le classi derivate non possono avere maggiore accessibilità rispetto ai relativi tipi di base. Non è possibile dichiarare una classe pubblica `B` che deriva da una classe interna `A`. Se consentito, avrebbe l'effetto di rendere `A` pubblico perché tutti i membri `protected` o `internal` di `A` sono accessibili dalla classe derivata.

È possibile abilitare altri assembly specifici per accedere ai tipi interni usando il `InternalsVisibleToAttribute`. Per altre informazioni, vedere [Friend Assemblies](../../../standard/assembly/friend.md) (Assembly friend).

## <a name="class-and-struct-member-accessibility"></a>Accessibilità membri classe e struct  

I membri di classe (inclusi le classi e gli struct annidati) possono essere dichiarati con uno qualsiasi dei sei tipi di accesso. I membri struct non possono essere dichiarati come `protected`, `protected internal`o `private protected` perché gli struct non supportano l'ereditarietà.

In genere, l'accessibilità di un membro non è maggiore dell'accessibilità del tipo che lo contiene. Tuttavia, un membro `public` di una classe interna potrebbe essere accessibile dall'esterno dell'assembly se il membro implementa metodi di interfaccia o esegue l'override di metodi virtuali definiti in una classe di base pubblica.

Il tipo di qualsiasi campo, proprietà o evento del membro deve essere accessibile almeno quanto il membro stesso. Analogamente, il tipo restituito e i tipi di parametro di qualsiasi metodo, indicizzatore o delegato devono essere accessibili almeno quanto il membro stesso. Ad esempio, non è possibile avere un metodo di `public` `M` che restituisce una classe `C` a meno che non venga `public`anche `C`. Analogamente, non è possibile avere una proprietà `protected` di tipo `A` se `A` viene dichiarata come `private`.

Gli operatori definiti dall'utente devono essere sempre dichiarati come `public` e `static`. Per altre informazioni, vedere [Overload degli operatori](../../language-reference/operators/operator-overloading.md).

I finalizzatori non possono avere modificatori di accessibilità.

Per impostare il livello di accesso per un membro `class` o `struct`, aggiungere la parola chiave appropriata alla dichiarazione del membro, come illustrato nell'esempio seguente.

[!code-csharp[MethodAccess](~/samples/snippets/csharp/objectoriented/accessmodifiers.cs#MethodAccess)]

## <a name="other-types"></a>Altri tipi

Le interfacce dichiarate direttamente all'interno di uno spazio dei nomi possono essere `public` o `internal` e, proprio come le classi e gli struct, l'impostazione predefinita delle interfacce `internal` l'accesso. I membri di interfaccia sono `public` per impostazione predefinita perché lo scopo di un'interfaccia è quello di consentire ad altri tipi di accedere a una classe o uno struct. Le dichiarazioni dei membri di interfaccia possono includere qualsiasi modificatore di accesso. Questa operazione è particolarmente utile per i metodi statici per fornire implementazioni comuni necessarie a tutti gli implementatori di una classe.

I membri dell'enumerazione sono sempre `public`e nessun modificatore di accesso può essere applicato.

I delegati si comportano come classi e struct. Per impostazione predefinita, hanno accesso `internal` quando vengono dichiarati direttamente all'interno di uno spazio dei nomi e `private` l'accesso quando nidificato.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [Interfacce](../interfaces/index.md)
- [private](../../language-reference/keywords/private.md)
- [pubblico](../../language-reference/keywords/public.md)
- [internal](../../language-reference/keywords/internal.md)
- [protected](../../language-reference/keywords/protected.md)
- [protected internal](../../language-reference/keywords/protected-internal.md)
- [private protected](../../language-reference/keywords/private-protected.md)
- [class](../../language-reference/keywords/class.md)
- [struct](../../language-reference/builtin-types/struct.md)
- [interface](../../language-reference/keywords/interface.md)
