---
title: Raccolte di schemi ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: f0240e99d2420b0956d3c144f837b39e094bb78a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794725"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="e1c9e-102">Raccolte di schemi ODBC</span><span class="sxs-lookup"><span data-stu-id="e1c9e-102">ODBC Schema Collections</span></span>

<span data-ttu-id="e1c9e-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per driver ODBC per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="e1c9e-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="e1c9e-104">Driver ODBC di Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="e1c9e-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="e1c9e-105">Oltre alle raccolte di schemi comuni, il driver ODBC di Microsoft SQL Server supporta le seguenti raccolte di schemi specifici:</span><span class="sxs-lookup"><span data-stu-id="e1c9e-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="e1c9e-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="e1c9e-106">Tables</span></span>

- <span data-ttu-id="e1c9e-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="e1c9e-107">Indexes</span></span>

- <span data-ttu-id="e1c9e-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="e1c9e-108">Columns</span></span>

- <span data-ttu-id="e1c9e-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="e1c9e-109">Procedures</span></span>

- <span data-ttu-id="e1c9e-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e1c9e-110">ProcedureColumns</span></span>

- <span data-ttu-id="e1c9e-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e1c9e-111">ProcedureParameters</span></span>

- <span data-ttu-id="e1c9e-112">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="e1c9e-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="e1c9e-113">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="e1c9e-113">Tables and Views</span></span>

|<span data-ttu-id="e1c9e-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-114">ColumnName</span></span>|<span data-ttu-id="e1c9e-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="e1c9e-116">TABLE_CAT</span></span>|<span data-ttu-id="e1c9e-117">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-117">String</span></span>|
|<span data-ttu-id="e1c9e-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e1c9e-118">TABLE_SCHEM</span></span>|<span data-ttu-id="e1c9e-119">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-119">String</span></span>|
|<span data-ttu-id="e1c9e-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-120">TABLE_NAME</span></span>|<span data-ttu-id="e1c9e-121">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-121">String</span></span>|
|<span data-ttu-id="e1c9e-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-122">TABLE_TYPE</span></span>|<span data-ttu-id="e1c9e-123">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-123">String</span></span>|
|<span data-ttu-id="e1c9e-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-124">REMARKS</span></span>|<span data-ttu-id="e1c9e-125">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="e1c9e-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="e1c9e-126">Indexes</span></span>

|<span data-ttu-id="e1c9e-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-127">ColumnName</span></span>|<span data-ttu-id="e1c9e-128">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="e1c9e-129">TABLE_CAT</span></span>|<span data-ttu-id="e1c9e-130">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-130">String</span></span>|
|<span data-ttu-id="e1c9e-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e1c9e-131">TABLE_SCHEM</span></span>|<span data-ttu-id="e1c9e-132">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-132">String</span></span>|
|<span data-ttu-id="e1c9e-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-133">TABLE_NAME</span></span>|<span data-ttu-id="e1c9e-134">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-134">String</span></span>|
|<span data-ttu-id="e1c9e-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-135">NON_UNIQUE</span></span>|<span data-ttu-id="e1c9e-136">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-136">Int16</span></span>|
|<span data-ttu-id="e1c9e-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="e1c9e-138">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-138">String</span></span>|
|<span data-ttu-id="e1c9e-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-139">INDEX_NAME</span></span>|<span data-ttu-id="e1c9e-140">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-140">String</span></span>|
|<span data-ttu-id="e1c9e-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-141">TYPE</span></span>|<span data-ttu-id="e1c9e-142">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-142">Int16</span></span>|
|<span data-ttu-id="e1c9e-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e1c9e-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="e1c9e-144">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-144">Int16</span></span>|
|<span data-ttu-id="e1c9e-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-145">COLUMN_NAME</span></span>|<span data-ttu-id="e1c9e-146">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-146">String</span></span>|
|<span data-ttu-id="e1c9e-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="e1c9e-147">ASC_OR_DESC</span></span>|<span data-ttu-id="e1c9e-148">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-148">String</span></span>|
|<span data-ttu-id="e1c9e-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="e1c9e-149">CARDINALITY</span></span>|<span data-ttu-id="e1c9e-150">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-150">Int32</span></span>|
|<span data-ttu-id="e1c9e-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="e1c9e-151">PAGES</span></span>|<span data-ttu-id="e1c9e-152">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-152">Int32</span></span>|
|<span data-ttu-id="e1c9e-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e1c9e-153">FILTER_CONDITION</span></span>|<span data-ttu-id="e1c9e-154">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-154">String</span></span>|
|<span data-ttu-id="e1c9e-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e1c9e-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e1c9e-156">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-156">String</span></span>|
|<span data-ttu-id="e1c9e-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-158">Byte</span><span class="sxs-lookup"><span data-stu-id="e1c9e-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="e1c9e-159">Colonne</span><span class="sxs-lookup"><span data-stu-id="e1c9e-159">Columns</span></span>

|<span data-ttu-id="e1c9e-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-160">ColumnName</span></span>|<span data-ttu-id="e1c9e-161">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="e1c9e-162">TABLE_CAT</span></span>|<span data-ttu-id="e1c9e-163">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-163">String</span></span>|
|<span data-ttu-id="e1c9e-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e1c9e-164">TABLE_SCHEM</span></span>|<span data-ttu-id="e1c9e-165">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-165">String</span></span>|
|<span data-ttu-id="e1c9e-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-166">TABLE_NAME</span></span>|<span data-ttu-id="e1c9e-167">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-167">String</span></span>|
|<span data-ttu-id="e1c9e-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-168">COLUMN_NAME</span></span>|<span data-ttu-id="e1c9e-169">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-169">String</span></span>|
|<span data-ttu-id="e1c9e-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-170">DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-171">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-171">Int16</span></span>|
|<span data-ttu-id="e1c9e-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-172">TYPE_NAME</span></span>|<span data-ttu-id="e1c9e-173">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-173">String</span></span>|
|<span data-ttu-id="e1c9e-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-174">COLUMN_SIZE</span></span>|<span data-ttu-id="e1c9e-175">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-175">Int32</span></span>|
|<span data-ttu-id="e1c9e-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e1c9e-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="e1c9e-177">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-177">Int32</span></span>|
|<span data-ttu-id="e1c9e-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e1c9e-179">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-179">Int16</span></span>|
|<span data-ttu-id="e1c9e-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e1c9e-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e1c9e-181">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-181">Int16</span></span>|
|<span data-ttu-id="e1c9e-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-182">NULLABLE</span></span>|<span data-ttu-id="e1c9e-183">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-183">Int16</span></span>|
|<span data-ttu-id="e1c9e-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-184">REMARKS</span></span>|<span data-ttu-id="e1c9e-185">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-185">String</span></span>|
|<span data-ttu-id="e1c9e-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e1c9e-186">COLUMN_DEF</span></span>|<span data-ttu-id="e1c9e-187">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-187">String</span></span>|
|<span data-ttu-id="e1c9e-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-189">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-189">Int16</span></span>|
|<span data-ttu-id="e1c9e-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e1c9e-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e1c9e-191">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-191">Int16</span></span>|
|<span data-ttu-id="e1c9e-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e1c9e-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e1c9e-193">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-193">Int32</span></span>|
|<span data-ttu-id="e1c9e-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e1c9e-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="e1c9e-195">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-195">Int32</span></span>|
|<span data-ttu-id="e1c9e-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-196">IS_NULLABLE</span></span>|<span data-ttu-id="e1c9e-197">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-197">String</span></span>|
|<span data-ttu-id="e1c9e-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e1c9e-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="e1c9e-199">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-199">String</span></span>|
|<span data-ttu-id="e1c9e-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e1c9e-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e1c9e-201">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-201">String</span></span>|
|<span data-ttu-id="e1c9e-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-203">Byte</span><span class="sxs-lookup"><span data-stu-id="e1c9e-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="e1c9e-204">Procedure</span><span class="sxs-lookup"><span data-stu-id="e1c9e-204">Procedures</span></span>

|<span data-ttu-id="e1c9e-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-205">ColumnName</span></span>|<span data-ttu-id="e1c9e-206">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e1c9e-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="e1c9e-208">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-208">String</span></span>|
|<span data-ttu-id="e1c9e-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e1c9e-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e1c9e-210">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-210">String</span></span>|
|<span data-ttu-id="e1c9e-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="e1c9e-212">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-212">String</span></span>|
|<span data-ttu-id="e1c9e-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="e1c9e-214">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-214">Int32</span></span>|
|<span data-ttu-id="e1c9e-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="e1c9e-216">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-216">Int32</span></span>|
|<span data-ttu-id="e1c9e-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="e1c9e-218">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-218">Int32</span></span>|
|<span data-ttu-id="e1c9e-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-219">REMARKS</span></span>|<span data-ttu-id="e1c9e-220">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-220">String</span></span>|
|<span data-ttu-id="e1c9e-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e1c9e-222">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="e1c9e-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e1c9e-223">ProcedureColumns</span></span>

|<span data-ttu-id="e1c9e-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-224">ColumnName</span></span>|<span data-ttu-id="e1c9e-225">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e1c9e-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="e1c9e-227">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-227">String</span></span>|
|<span data-ttu-id="e1c9e-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e1c9e-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e1c9e-229">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-229">String</span></span>|
|<span data-ttu-id="e1c9e-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="e1c9e-231">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-231">String</span></span>|
|<span data-ttu-id="e1c9e-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-232">COLUMN_NAME</span></span>|<span data-ttu-id="e1c9e-233">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-233">String</span></span>|
|<span data-ttu-id="e1c9e-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-234">COLUMN_TYPE</span></span>|<span data-ttu-id="e1c9e-235">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-235">Int16</span></span>|
|<span data-ttu-id="e1c9e-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-236">DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-237">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-237">Int16</span></span>|
|<span data-ttu-id="e1c9e-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-238">TYPE_NAME</span></span>|<span data-ttu-id="e1c9e-239">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-239">String</span></span>|
|<span data-ttu-id="e1c9e-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-240">COLUMN_SIZE</span></span>|<span data-ttu-id="e1c9e-241">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-241">Int32</span></span>|
|<span data-ttu-id="e1c9e-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e1c9e-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="e1c9e-243">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-243">Int32</span></span>|
|<span data-ttu-id="e1c9e-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e1c9e-245">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-245">Int16</span></span>|
|<span data-ttu-id="e1c9e-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e1c9e-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e1c9e-247">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-247">Int16</span></span>|
|<span data-ttu-id="e1c9e-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-248">NULLABLE</span></span>|<span data-ttu-id="e1c9e-249">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-249">Int16</span></span>|
|<span data-ttu-id="e1c9e-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-250">REMARKS</span></span>|<span data-ttu-id="e1c9e-251">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-251">String</span></span>|
|<span data-ttu-id="e1c9e-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e1c9e-252">COLUMN_DEF</span></span>|<span data-ttu-id="e1c9e-253">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-253">String</span></span>|
|<span data-ttu-id="e1c9e-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-255">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-255">Int16</span></span>|
|<span data-ttu-id="e1c9e-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e1c9e-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e1c9e-257">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-257">Int16</span></span>|
|<span data-ttu-id="e1c9e-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e1c9e-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e1c9e-259">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-259">Int32</span></span>|
|<span data-ttu-id="e1c9e-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e1c9e-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="e1c9e-261">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-261">Int32</span></span>|
|<span data-ttu-id="e1c9e-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-262">IS_NULLABLE</span></span>|<span data-ttu-id="e1c9e-263">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-263">String</span></span>|
|<span data-ttu-id="e1c9e-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e1c9e-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="e1c9e-265">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-265">String</span></span>|
|<span data-ttu-id="e1c9e-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e1c9e-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e1c9e-267">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-267">String</span></span>|
|<span data-ttu-id="e1c9e-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-269">Byte</span><span class="sxs-lookup"><span data-stu-id="e1c9e-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="e1c9e-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e1c9e-270">ProcedureParameters</span></span>

|<span data-ttu-id="e1c9e-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-271">ColumnName</span></span>|<span data-ttu-id="e1c9e-272">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e1c9e-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="e1c9e-274">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-274">String</span></span>|
|<span data-ttu-id="e1c9e-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e1c9e-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e1c9e-276">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-276">String</span></span>|
|<span data-ttu-id="e1c9e-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="e1c9e-278">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-278">String</span></span>|
|<span data-ttu-id="e1c9e-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-279">COLUMN_NAME</span></span>|<span data-ttu-id="e1c9e-280">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-280">String</span></span>|
|<span data-ttu-id="e1c9e-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-281">COLUMN_TYPE</span></span>|<span data-ttu-id="e1c9e-282">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-282">Int16</span></span>|
|<span data-ttu-id="e1c9e-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-283">DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-284">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-284">Int16</span></span>|
|<span data-ttu-id="e1c9e-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-285">TYPE_NAME</span></span>|<span data-ttu-id="e1c9e-286">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-286">String</span></span>|
|<span data-ttu-id="e1c9e-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-287">COLUMN_SIZE</span></span>|<span data-ttu-id="e1c9e-288">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-288">Int32</span></span>|
|<span data-ttu-id="e1c9e-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e1c9e-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="e1c9e-290">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-290">Int32</span></span>|
|<span data-ttu-id="e1c9e-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e1c9e-292">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-292">Int16</span></span>|
|<span data-ttu-id="e1c9e-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e1c9e-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e1c9e-294">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-294">Int16</span></span>|
|<span data-ttu-id="e1c9e-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-295">NULLABLE</span></span>|<span data-ttu-id="e1c9e-296">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-296">Int16</span></span>|
|<span data-ttu-id="e1c9e-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-297">REMARKS</span></span>|<span data-ttu-id="e1c9e-298">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-298">String</span></span>|
|<span data-ttu-id="e1c9e-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e1c9e-299">COLUMN_DEF</span></span>|<span data-ttu-id="e1c9e-300">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-300">String</span></span>|
|<span data-ttu-id="e1c9e-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-302">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-302">Int16</span></span>|
|<span data-ttu-id="e1c9e-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e1c9e-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e1c9e-304">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-304">Int16</span></span>|
|<span data-ttu-id="e1c9e-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e1c9e-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e1c9e-306">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-306">Int32</span></span>|
|<span data-ttu-id="e1c9e-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e1c9e-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="e1c9e-308">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-308">Int32</span></span>|
|<span data-ttu-id="e1c9e-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-309">IS_NULLABLE</span></span>|<span data-ttu-id="e1c9e-310">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-310">String</span></span>|
|<span data-ttu-id="e1c9e-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e1c9e-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="e1c9e-312">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-312">String</span></span>|
|<span data-ttu-id="e1c9e-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e1c9e-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e1c9e-314">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-314">String</span></span>|
|<span data-ttu-id="e1c9e-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-316">Byte</span><span class="sxs-lookup"><span data-stu-id="e1c9e-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="e1c9e-317">Driver Microsoft ODBC per Oracle</span><span class="sxs-lookup"><span data-stu-id="e1c9e-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="e1c9e-318">Oltre alle raccolte di schemi comuni, il driver ODBC di Microsoft SQL Server Oracle supporta le seguenti raccolte di schemi specifici:</span><span class="sxs-lookup"><span data-stu-id="e1c9e-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="e1c9e-319">Tabelle</span><span class="sxs-lookup"><span data-stu-id="e1c9e-319">Tables</span></span>

- <span data-ttu-id="e1c9e-320">Colonne</span><span class="sxs-lookup"><span data-stu-id="e1c9e-320">Columns</span></span>

- <span data-ttu-id="e1c9e-321">Procedure</span><span class="sxs-lookup"><span data-stu-id="e1c9e-321">Procedures</span></span>

- <span data-ttu-id="e1c9e-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e1c9e-322">ProcedureColumns</span></span>

- <span data-ttu-id="e1c9e-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e1c9e-323">ProcedureParameters</span></span>

- <span data-ttu-id="e1c9e-324">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="e1c9e-324">Views</span></span>

- <span data-ttu-id="e1c9e-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="e1c9e-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="e1c9e-326">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="e1c9e-326">Tables and Views</span></span>

|<span data-ttu-id="e1c9e-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-327">ColumnName</span></span>|<span data-ttu-id="e1c9e-328">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e1c9e-330">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-330">String</span></span>|
|<span data-ttu-id="e1c9e-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-331">TABLE_OWNER</span></span>|<span data-ttu-id="e1c9e-332">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-332">String</span></span>|
|<span data-ttu-id="e1c9e-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-333">TABLE_NAME</span></span>|<span data-ttu-id="e1c9e-334">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-334">String</span></span>|
|<span data-ttu-id="e1c9e-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-335">TABLE_TYPE</span></span>|<span data-ttu-id="e1c9e-336">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-336">String</span></span>|
|<span data-ttu-id="e1c9e-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-337">REMARKS</span></span>|<span data-ttu-id="e1c9e-338">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="e1c9e-339">Colonne</span><span class="sxs-lookup"><span data-stu-id="e1c9e-339">Columns</span></span>

|<span data-ttu-id="e1c9e-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-340">ColumnName</span></span>|<span data-ttu-id="e1c9e-341">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e1c9e-343">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-343">String</span></span>|
|<span data-ttu-id="e1c9e-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-344">TABLE_OWNER</span></span>|<span data-ttu-id="e1c9e-345">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-345">String</span></span>|
|<span data-ttu-id="e1c9e-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-346">TABLE_NAME</span></span>|<span data-ttu-id="e1c9e-347">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-347">String</span></span>|
|<span data-ttu-id="e1c9e-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-348">COLUMN_NAME</span></span>|<span data-ttu-id="e1c9e-349">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-349">String</span></span>|
|<span data-ttu-id="e1c9e-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-350">DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-351">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-351">Int16</span></span>|
|<span data-ttu-id="e1c9e-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-352">TYPE_NAME</span></span>|<span data-ttu-id="e1c9e-353">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-353">String</span></span>|
|<span data-ttu-id="e1c9e-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e1c9e-354">PRECISION</span></span>|<span data-ttu-id="e1c9e-355">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-355">Int32</span></span>|
|<span data-ttu-id="e1c9e-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e1c9e-356">LENGTH</span></span>|<span data-ttu-id="e1c9e-357">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-357">Int32</span></span>|
|<span data-ttu-id="e1c9e-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-358">SCALE</span></span>|<span data-ttu-id="e1c9e-359">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-359">Int16</span></span>|
|<span data-ttu-id="e1c9e-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="e1c9e-360">RADIX</span></span>|<span data-ttu-id="e1c9e-361">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-361">Int16</span></span>|
|<span data-ttu-id="e1c9e-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-362">NULLABLE</span></span>|<span data-ttu-id="e1c9e-363">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-363">Int16</span></span>|
|<span data-ttu-id="e1c9e-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-364">REMARKS</span></span>|<span data-ttu-id="e1c9e-365">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-365">String</span></span>|
|<span data-ttu-id="e1c9e-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e1c9e-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="e1c9e-367">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="e1c9e-368">Procedure</span><span class="sxs-lookup"><span data-stu-id="e1c9e-368">Procedures</span></span>

|<span data-ttu-id="e1c9e-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-369">ColumnName</span></span>|<span data-ttu-id="e1c9e-370">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e1c9e-372">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-372">String</span></span>|
|<span data-ttu-id="e1c9e-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e1c9e-374">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-374">String</span></span>|
|<span data-ttu-id="e1c9e-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="e1c9e-376">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-376">String</span></span>|
|<span data-ttu-id="e1c9e-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="e1c9e-378">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-378">Int16</span></span>|
|<span data-ttu-id="e1c9e-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="e1c9e-380">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-380">Int16</span></span>|
|<span data-ttu-id="e1c9e-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="e1c9e-382">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-382">Int16</span></span>|
|<span data-ttu-id="e1c9e-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-383">REMARKS</span></span>|<span data-ttu-id="e1c9e-384">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-384">String</span></span>|
|<span data-ttu-id="e1c9e-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e1c9e-386">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="e1c9e-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e1c9e-387">ProcedureColumns</span></span>

|<span data-ttu-id="e1c9e-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-388">ColumnName</span></span>|<span data-ttu-id="e1c9e-389">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e1c9e-391">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-391">String</span></span>|
|<span data-ttu-id="e1c9e-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e1c9e-393">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-393">String</span></span>|
|<span data-ttu-id="e1c9e-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="e1c9e-395">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-395">String</span></span>|
|<span data-ttu-id="e1c9e-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-396">COLUMN_NAME</span></span>|<span data-ttu-id="e1c9e-397">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-397">String</span></span>|
|<span data-ttu-id="e1c9e-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-398">COLUMN_TYPE</span></span>|<span data-ttu-id="e1c9e-399">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-399">Int16</span></span>|
|<span data-ttu-id="e1c9e-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-400">DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-401">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-401">Int16</span></span>|
|<span data-ttu-id="e1c9e-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-402">TYPE_NAME</span></span>|<span data-ttu-id="e1c9e-403">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-403">String</span></span>|
|<span data-ttu-id="e1c9e-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e1c9e-404">PRECISION</span></span>|<span data-ttu-id="e1c9e-405">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-405">Int32</span></span>|
|<span data-ttu-id="e1c9e-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e1c9e-406">LENGTH</span></span>|<span data-ttu-id="e1c9e-407">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-407">Int32</span></span>|
|<span data-ttu-id="e1c9e-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-408">SCALE</span></span>|<span data-ttu-id="e1c9e-409">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-409">Int16</span></span>|
|<span data-ttu-id="e1c9e-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="e1c9e-410">RADIX</span></span>|<span data-ttu-id="e1c9e-411">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-411">Int16</span></span>|
|<span data-ttu-id="e1c9e-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-412">NULLABLE</span></span>|<span data-ttu-id="e1c9e-413">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-413">Int16</span></span>|
|<span data-ttu-id="e1c9e-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-414">REMARKS</span></span>|<span data-ttu-id="e1c9e-415">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-415">String</span></span>|
|<span data-ttu-id="e1c9e-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="e1c9e-416">OVERLOAD</span></span>|<span data-ttu-id="e1c9e-417">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-417">Int32</span></span>|
|<span data-ttu-id="e1c9e-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e1c9e-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="e1c9e-419">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="e1c9e-420">Driver ODBC per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="e1c9e-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="e1c9e-421">Oltre alle raccolte di schemi comuni, il driver ODBC per Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1c9e-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="e1c9e-422">Tabelle</span><span class="sxs-lookup"><span data-stu-id="e1c9e-422">Tables</span></span>

- <span data-ttu-id="e1c9e-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="e1c9e-423">Indexes</span></span>

- <span data-ttu-id="e1c9e-424">Colonne</span><span class="sxs-lookup"><span data-stu-id="e1c9e-424">Columns</span></span>

- <span data-ttu-id="e1c9e-425">Procedure</span><span class="sxs-lookup"><span data-stu-id="e1c9e-425">Procedures</span></span>

- <span data-ttu-id="e1c9e-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e1c9e-426">ProcedureColumns</span></span>

- <span data-ttu-id="e1c9e-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e1c9e-427">ProcedureParameters</span></span>

- <span data-ttu-id="e1c9e-428">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="e1c9e-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="e1c9e-429">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="e1c9e-429">Tables and Views</span></span>

|<span data-ttu-id="e1c9e-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-430">ColumnName</span></span>|<span data-ttu-id="e1c9e-431">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e1c9e-433">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-433">String</span></span>|
|<span data-ttu-id="e1c9e-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-434">TABLE_OWNER</span></span>|<span data-ttu-id="e1c9e-435">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-435">String</span></span>|
|<span data-ttu-id="e1c9e-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-436">TABLE_NAME</span></span>|<span data-ttu-id="e1c9e-437">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-437">String</span></span>|
|<span data-ttu-id="e1c9e-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-438">TABLE_TYPE</span></span>|<span data-ttu-id="e1c9e-439">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-439">String</span></span>|
|<span data-ttu-id="e1c9e-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-440">REMARKS</span></span>|<span data-ttu-id="e1c9e-441">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="e1c9e-442">Colonne</span><span class="sxs-lookup"><span data-stu-id="e1c9e-442">Columns</span></span>

|<span data-ttu-id="e1c9e-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-443">ColumnName</span></span>|<span data-ttu-id="e1c9e-444">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e1c9e-446">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-446">String</span></span>|
|<span data-ttu-id="e1c9e-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-447">TABLE_OWNER</span></span>|<span data-ttu-id="e1c9e-448">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-448">String</span></span>|
|<span data-ttu-id="e1c9e-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-449">TABLE_NAME</span></span>|<span data-ttu-id="e1c9e-450">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-450">String</span></span>|
|<span data-ttu-id="e1c9e-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-451">COLUMN_NAME</span></span>|<span data-ttu-id="e1c9e-452">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-452">String</span></span>|
|<span data-ttu-id="e1c9e-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-453">DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-454">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-454">Int16</span></span>|
|<span data-ttu-id="e1c9e-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-455">TYPE_NAME</span></span>|<span data-ttu-id="e1c9e-456">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-456">String</span></span>|
|<span data-ttu-id="e1c9e-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e1c9e-457">PRECISION</span></span>|<span data-ttu-id="e1c9e-458">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-458">Int32</span></span>|
|<span data-ttu-id="e1c9e-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e1c9e-459">LENGTH</span></span>|<span data-ttu-id="e1c9e-460">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-460">Int32</span></span>|
|<span data-ttu-id="e1c9e-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-461">SCALE</span></span>|<span data-ttu-id="e1c9e-462">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-462">Int16</span></span>|
|<span data-ttu-id="e1c9e-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="e1c9e-463">RADIX</span></span>|<span data-ttu-id="e1c9e-464">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-464">Int16</span></span>|
|<span data-ttu-id="e1c9e-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-465">NULLABLE</span></span>|<span data-ttu-id="e1c9e-466">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-466">Int16</span></span>|
|<span data-ttu-id="e1c9e-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-467">REMARKS</span></span>|<span data-ttu-id="e1c9e-468">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-468">String</span></span>|
|<span data-ttu-id="e1c9e-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e1c9e-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="e1c9e-470">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="e1c9e-471">Procedure</span><span class="sxs-lookup"><span data-stu-id="e1c9e-471">Procedures</span></span>

|<span data-ttu-id="e1c9e-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-472">ColumnName</span></span>|<span data-ttu-id="e1c9e-473">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e1c9e-475">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-475">String</span></span>|
|<span data-ttu-id="e1c9e-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e1c9e-477">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-477">String</span></span>|
|<span data-ttu-id="e1c9e-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="e1c9e-479">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-479">String</span></span>|
|<span data-ttu-id="e1c9e-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="e1c9e-481">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-481">Int16</span></span>|
|<span data-ttu-id="e1c9e-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="e1c9e-483">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-483">Int16</span></span>|
|<span data-ttu-id="e1c9e-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="e1c9e-485">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-485">Int16</span></span>|
|<span data-ttu-id="e1c9e-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-486">REMARKS</span></span>|<span data-ttu-id="e1c9e-487">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-487">String</span></span>|
|<span data-ttu-id="e1c9e-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e1c9e-489">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="e1c9e-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e1c9e-490">ProcedureColumns</span></span>

|<span data-ttu-id="e1c9e-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-491">ColumnName</span></span>|<span data-ttu-id="e1c9e-492">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e1c9e-494">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-494">String</span></span>|
|<span data-ttu-id="e1c9e-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1c9e-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e1c9e-496">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-496">String</span></span>|
|<span data-ttu-id="e1c9e-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="e1c9e-498">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-498">String</span></span>|
|<span data-ttu-id="e1c9e-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-499">COLUMN_NAME</span></span>|<span data-ttu-id="e1c9e-500">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-500">String</span></span>|
|<span data-ttu-id="e1c9e-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-501">COLUMN_TYPE</span></span>|<span data-ttu-id="e1c9e-502">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-502">Int16</span></span>|
|<span data-ttu-id="e1c9e-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-503">DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-504">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-504">Int16</span></span>|
|<span data-ttu-id="e1c9e-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-505">TYPE_NAME</span></span>|<span data-ttu-id="e1c9e-506">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-506">String</span></span>|
|<span data-ttu-id="e1c9e-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e1c9e-507">PRECISION</span></span>|<span data-ttu-id="e1c9e-508">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-508">Int32</span></span>|
|<span data-ttu-id="e1c9e-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e1c9e-509">LENGTH</span></span>|<span data-ttu-id="e1c9e-510">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-510">Int32</span></span>|
|<span data-ttu-id="e1c9e-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-511">SCALE</span></span>|<span data-ttu-id="e1c9e-512">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-512">Int16</span></span>|
|<span data-ttu-id="e1c9e-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="e1c9e-513">RADIX</span></span>|<span data-ttu-id="e1c9e-514">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-514">Int16</span></span>|
|<span data-ttu-id="e1c9e-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-515">NULLABLE</span></span>|<span data-ttu-id="e1c9e-516">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-516">Int16</span></span>|
|<span data-ttu-id="e1c9e-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-517">REMARKS</span></span>|<span data-ttu-id="e1c9e-518">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-518">String</span></span>|
|<span data-ttu-id="e1c9e-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="e1c9e-519">OVERLOAD</span></span>|<span data-ttu-id="e1c9e-520">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-520">Int32</span></span>|
|<span data-ttu-id="e1c9e-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e1c9e-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="e1c9e-522">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="e1c9e-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e1c9e-523">ProcedureParameters</span></span>

|<span data-ttu-id="e1c9e-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e1c9e-524">ColumnName</span></span>|<span data-ttu-id="e1c9e-525">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1c9e-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="e1c9e-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e1c9e-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="e1c9e-527">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-527">String</span></span>|
|<span data-ttu-id="e1c9e-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e1c9e-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e1c9e-529">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-529">String</span></span>|
|<span data-ttu-id="e1c9e-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="e1c9e-531">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-531">String</span></span>|
|<span data-ttu-id="e1c9e-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-532">COLUMN_NAME</span></span>|<span data-ttu-id="e1c9e-533">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-533">String</span></span>|
|<span data-ttu-id="e1c9e-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-534">COLUMN_TYPE</span></span>|<span data-ttu-id="e1c9e-535">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-535">Int16</span></span>|
|<span data-ttu-id="e1c9e-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-536">DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-537">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-537">Int16</span></span>|
|<span data-ttu-id="e1c9e-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e1c9e-538">TYPE_NAME</span></span>|<span data-ttu-id="e1c9e-539">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-539">String</span></span>|
|<span data-ttu-id="e1c9e-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-540">COLUMN_SIZE</span></span>|<span data-ttu-id="e1c9e-541">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-541">Int32</span></span>|
|<span data-ttu-id="e1c9e-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e1c9e-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="e1c9e-543">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-543">Int32</span></span>|
|<span data-ttu-id="e1c9e-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e1c9e-545">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-545">Int16</span></span>|
|<span data-ttu-id="e1c9e-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e1c9e-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e1c9e-547">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-547">Int16</span></span>|
|<span data-ttu-id="e1c9e-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-548">NULLABLE</span></span>|<span data-ttu-id="e1c9e-549">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-549">Int16</span></span>|
|<span data-ttu-id="e1c9e-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e1c9e-550">REMARKS</span></span>|<span data-ttu-id="e1c9e-551">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-551">String</span></span>|
|<span data-ttu-id="e1c9e-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e1c9e-552">COLUMN_DEF</span></span>|<span data-ttu-id="e1c9e-553">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-553">String</span></span>|
|<span data-ttu-id="e1c9e-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e1c9e-555">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-555">Int16</span></span>|
|<span data-ttu-id="e1c9e-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e1c9e-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e1c9e-557">Int16</span><span class="sxs-lookup"><span data-stu-id="e1c9e-557">Int16</span></span>|
|<span data-ttu-id="e1c9e-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e1c9e-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e1c9e-559">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-559">Int32</span></span>|
|<span data-ttu-id="e1c9e-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e1c9e-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="e1c9e-561">Int32</span><span class="sxs-lookup"><span data-stu-id="e1c9e-561">Int32</span></span>|
|<span data-ttu-id="e1c9e-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e1c9e-562">IS_NULLABLE</span></span>|<span data-ttu-id="e1c9e-563">String</span><span class="sxs-lookup"><span data-stu-id="e1c9e-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="e1c9e-564">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1c9e-564">See also</span></span>

- [<span data-ttu-id="e1c9e-565">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e1c9e-565">ADO.NET Overview</span></span>](ado-net-overview.md)
