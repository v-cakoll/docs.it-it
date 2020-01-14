---
title: API non supportate in .NET Core
description: Informazioni sulle API del .NET Framework che generano sempre un'eccezione in .NET Core.
ms.date: 12/23/2019
ms.openlocfilehash: f27aeca31226a95dacf100813762eedb56876fbd
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936978"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="09665-103">API che generano sempre eccezioni in .NET Core</span><span class="sxs-lookup"><span data-stu-id="09665-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="09665-104">Le API seguenti genereranno sempre un <xref:System.PlatformNotSupportedException> in .NET Core su tutti o un subset di piattaforme.</span><span class="sxs-lookup"><span data-stu-id="09665-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET Core on all or a subset of platforms.</span></span>

<span data-ttu-id="09665-105">Questo articolo organizza i membri API interessati in base allo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="09665-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="09665-106">Questo articolo è un lavoro in corso.</span><span class="sxs-lookup"><span data-stu-id="09665-106">This article is a work-in-progress.</span></span> <span data-ttu-id="09665-107">Non si tratta di un elenco completo di API che generano eccezioni in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09665-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="09665-108">Questo articolo non include le implementazioni esplicite dell'interfaccia per la serializzazione binaria generata in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09665-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="09665-109">Per altre informazioni, vedere [serializzazione binaria in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="09665-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="09665-110">System</span><span class="sxs-lookup"><span data-stu-id="09665-110">System</span></span>

| <span data-ttu-id="09665-111">Member</span><span class="sxs-lookup"><span data-stu-id="09665-111">Member</span></span> | <span data-ttu-id="09665-112">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-113">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="09665-114">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="09665-115">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="09665-116">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-117">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="09665-118">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="09665-119">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="09665-120">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-121">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="09665-122">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="09665-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="09665-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="09665-124">Member</span><span class="sxs-lookup"><span data-stu-id="09665-124">Member</span></span> | <span data-ttu-id="09665-125">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-126">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-127">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-128">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="09665-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="09665-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="09665-130">Member</span><span class="sxs-lookup"><span data-stu-id="09665-130">Member</span></span> | <span data-ttu-id="09665-131">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-132">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-133">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="09665-134">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="09665-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="09665-135">System.Configuration</span></span>

| <span data-ttu-id="09665-136">Member</span><span class="sxs-lookup"><span data-stu-id="09665-136">Member</span></span> | <span data-ttu-id="09665-137">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="09665-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (tutti i membri)</span><span class="sxs-lookup"><span data-stu-id="09665-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="09665-139">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="09665-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="09665-140">System.Console</span></span>

| <span data-ttu-id="09665-141">Member</span><span class="sxs-lookup"><span data-stu-id="09665-141">Member</span></span> | <span data-ttu-id="09665-142">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="09665-143">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-143">Linux and macOS</span></span> |
| <span data-ttu-id="09665-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="09665-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="09665-145">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-145">Linux and macOS</span></span> |
| <span data-ttu-id="09665-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="09665-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="09665-147">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-147">Linux and macOS</span></span> |
| <span data-ttu-id="09665-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="09665-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="09665-149">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-149">Linux and macOS</span></span> |
| <span data-ttu-id="09665-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (solo Get)</span><span class="sxs-lookup"><span data-stu-id="09665-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="09665-151">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-152">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-153">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-154">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-154">Linux and macOS</span></span> |
| <span data-ttu-id="09665-155"><xref:System.Console.Title?displayProperty=nameWithType> (solo Get)</span><span class="sxs-lookup"><span data-stu-id="09665-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="09665-156">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-156">Linux and macOS</span></span> |
| <span data-ttu-id="09665-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="09665-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="09665-158">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-158">Linux and macOS</span></span> |
| <span data-ttu-id="09665-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="09665-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="09665-160">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-160">Linux and macOS</span></span> |
| <span data-ttu-id="09665-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="09665-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="09665-162">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-162">Linux and macOS</span></span> |
| <span data-ttu-id="09665-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="09665-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="09665-164">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="09665-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="09665-165">System.Data.Common</span></span>

| <span data-ttu-id="09665-166">Member</span><span class="sxs-lookup"><span data-stu-id="09665-166">Member</span></span> | <span data-ttu-id="09665-167">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="09665-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (genera <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="09665-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="09665-169">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="09665-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="09665-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="09665-171">Member</span><span class="sxs-lookup"><span data-stu-id="09665-171">Member</span></span> | <span data-ttu-id="09665-172">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="09665-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="09665-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="09665-174">Linux</span><span class="sxs-lookup"><span data-stu-id="09665-174">Linux</span></span> |
| <span data-ttu-id="09665-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="09665-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="09665-176">Linux</span><span class="sxs-lookup"><span data-stu-id="09665-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="09665-177">macOS</span><span class="sxs-lookup"><span data-stu-id="09665-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="09665-178">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-179">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="09665-180">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="09665-181">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="09665-182">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="09665-183">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-183">Linux and macOS</span></span> |
| <span data-ttu-id="09665-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="09665-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="09665-185">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-185">Linux and macOS</span></span> |
| <span data-ttu-id="09665-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Get)</span><span class="sxs-lookup"><span data-stu-id="09665-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="09665-187">macOS</span><span class="sxs-lookup"><span data-stu-id="09665-187">macOS</span></span> |
| <span data-ttu-id="09665-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="09665-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="09665-189">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="09665-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="09665-190">System.IO</span></span>

| <span data-ttu-id="09665-191">Member</span><span class="sxs-lookup"><span data-stu-id="09665-191">Member</span></span> | <span data-ttu-id="09665-192">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-193">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-194">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="09665-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="09665-195">System.IO.Pipes</span></span>

| <span data-ttu-id="09665-196">Member</span><span class="sxs-lookup"><span data-stu-id="09665-196">Member</span></span> | <span data-ttu-id="09665-197">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="09665-198">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="09665-199">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="09665-200">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="09665-201">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-201">Linux and macOS</span></span> |
| <span data-ttu-id="09665-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="09665-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="09665-203">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="09665-204">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="09665-205">System. Media</span><span class="sxs-lookup"><span data-stu-id="09665-205">System.Media</span></span>

| <span data-ttu-id="09665-206">Member</span><span class="sxs-lookup"><span data-stu-id="09665-206">Member</span></span> | <span data-ttu-id="09665-207">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-208">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="09665-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="09665-209">System.Net</span></span>

| <span data-ttu-id="09665-210">Member</span><span class="sxs-lookup"><span data-stu-id="09665-210">Member</span></span> | <span data-ttu-id="09665-211">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="09665-212">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="09665-213">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-214">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-215">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-216">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-217">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-218">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-219">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-220">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-221">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-222">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="09665-223">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-224">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-225">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-226">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-227">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-228">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="09665-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="09665-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="09665-230">Member</span><span class="sxs-lookup"><span data-stu-id="09665-230">Member</span></span> | <span data-ttu-id="09665-231">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="09665-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="09665-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="09665-233">System.Net.Sockets</span></span>

| <span data-ttu-id="09665-234">Member</span><span class="sxs-lookup"><span data-stu-id="09665-234">Member</span></span> | <span data-ttu-id="09665-235">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="09665-236">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-236">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="09665-237">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="09665-237">System.Net.WebSockets</span></span>

| <span data-ttu-id="09665-238">Member</span><span class="sxs-lookup"><span data-stu-id="09665-238">Member</span></span> | <span data-ttu-id="09665-239">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-239">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="09665-240">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-240">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="09665-241">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="09665-241">System.Reflection</span></span>

| <span data-ttu-id="09665-242">Member</span><span class="sxs-lookup"><span data-stu-id="09665-242">Member</span></span> | <span data-ttu-id="09665-243">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-243">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-244">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-244">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="09665-245">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-245">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-246">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="09665-247">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-247">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | <span data-ttu-id="09665-248">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-249">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="09665-250">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-250">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="09665-251">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="09665-251">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="09665-252">Member</span><span class="sxs-lookup"><span data-stu-id="09665-252">Member</span></span> | <span data-ttu-id="09665-253">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-253">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="09665-254">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-254">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="09665-255">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="09665-255">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="09665-256">Member</span><span class="sxs-lookup"><span data-stu-id="09665-256">Member</span></span> | <span data-ttu-id="09665-257">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-257">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="09665-258">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-258">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="09665-259">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="09665-260">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="09665-261">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-261">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="09665-262">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-262">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="09665-263">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="09665-264">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-264">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="09665-265">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="09665-265">System.Runtime.Serialization</span></span>

| <span data-ttu-id="09665-266">Member</span><span class="sxs-lookup"><span data-stu-id="09665-266">Member</span></span> | <span data-ttu-id="09665-267">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-267">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="09665-268">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-268">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="09665-269">System.Security</span><span class="sxs-lookup"><span data-stu-id="09665-269">System.Security</span></span>

| <span data-ttu-id="09665-270">Member</span><span class="sxs-lookup"><span data-stu-id="09665-270">Member</span></span> | <span data-ttu-id="09665-271">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-271">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="09665-272">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-272">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="09665-273">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-273">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="09665-274">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-274">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="09665-275">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-275">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="09665-276">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-276">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="09665-277">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-277">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="09665-278">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-278">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="09665-279">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-279">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="09665-280">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="09665-281">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-281">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="09665-282">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-282">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="09665-283">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-283">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="09665-284">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="09665-285">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-285">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="09665-286">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="09665-286">System.Security.Claims</span></span>

| <span data-ttu-id="09665-287">Member</span><span class="sxs-lookup"><span data-stu-id="09665-287">Member</span></span> | <span data-ttu-id="09665-288">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-288">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | <span data-ttu-id="09665-289">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-289">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-290">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | <span data-ttu-id="09665-291">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-292">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-293">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-293">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="09665-294">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="09665-294">System.Security.Cryptography</span></span>

| <span data-ttu-id="09665-295">Member</span><span class="sxs-lookup"><span data-stu-id="09665-295">Member</span></span> | <span data-ttu-id="09665-296">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-296">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="09665-297">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-297">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-298">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-298">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="09665-299">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="09665-300">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="09665-301">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="09665-302">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="09665-303">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="09665-304">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="09665-305">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="09665-306">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="09665-307">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="09665-308">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="09665-309">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="09665-310">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="09665-311">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-311">All</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="09665-312">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="09665-313">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="09665-314">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-315">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-316">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-317">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="09665-318">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="09665-319">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-320">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-321">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="09665-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-322">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-323">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="09665-324">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="09665-325">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="09665-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="09665-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="09665-327">Member</span><span class="sxs-lookup"><span data-stu-id="09665-327">Member</span></span> | <span data-ttu-id="09665-328">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | <span data-ttu-id="09665-329">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="09665-330">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="09665-331">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="09665-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="09665-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="09665-333">Member</span><span class="sxs-lookup"><span data-stu-id="09665-333">Member</span></span> | <span data-ttu-id="09665-334">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-335">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-336">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-337">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-337">All</span></span> |
| <span data-ttu-id="09665-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="09665-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="09665-339">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="09665-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="09665-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="09665-341">Member</span><span class="sxs-lookup"><span data-stu-id="09665-341">Member</span></span> | <span data-ttu-id="09665-342">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-343">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="09665-344">System. Security. Policy</span><span class="sxs-lookup"><span data-stu-id="09665-344">System.Security.Policy</span></span>

| <span data-ttu-id="09665-345">Member</span><span class="sxs-lookup"><span data-stu-id="09665-345">Member</span></span> | <span data-ttu-id="09665-346">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-347">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="09665-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="09665-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="09665-349">Member</span><span class="sxs-lookup"><span data-stu-id="09665-349">Member</span></span> | <span data-ttu-id="09665-350">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-351">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="09665-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="09665-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="09665-353">Member</span><span class="sxs-lookup"><span data-stu-id="09665-353">Member</span></span> | <span data-ttu-id="09665-354">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-355">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="09665-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="09665-356">System.Threading</span></span>

| <span data-ttu-id="09665-357">Member</span><span class="sxs-lookup"><span data-stu-id="09665-357">Member</span></span> | <span data-ttu-id="09665-358">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-359">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="09665-360">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="09665-361">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="09665-362">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="09665-363">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="09665-364">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="09665-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="09665-365">System.Xml</span></span>

| <span data-ttu-id="09665-366">Member</span><span class="sxs-lookup"><span data-stu-id="09665-366">Member</span></span> | <span data-ttu-id="09665-367">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="09665-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="09665-368">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="09665-369">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="09665-370">Tutte le</span><span class="sxs-lookup"><span data-stu-id="09665-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="09665-371">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09665-371">See also</span></span>

- [<span data-ttu-id="09665-372">Modifiche di rilievo per la migrazione da .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="09665-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="09665-373">Serializzazione binaria in .NET Core</span><span class="sxs-lookup"><span data-stu-id="09665-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="09665-374">.NET Portability Analyzer</span><span class="sxs-lookup"><span data-stu-id="09665-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
