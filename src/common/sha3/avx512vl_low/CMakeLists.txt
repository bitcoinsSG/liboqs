# Copyright (c) 2025 Intel Corporation
#
# SPDX-License-Identifier: MIT

set(_SHA3_AVX512VL_LOW_OBJS "")

if(OQS_USE_SHA3_AVX512VL)
  add_library(sha3_avx512vl_low OBJECT
    KeccakP-1600-AVX512VL.S SHA3-AVX512VL.S KeccakP-1600-times4-AVX512VL.S SHA3-times4-AVX512VL.S)
  set(_SHA3_AVX512VL_LOW_OBJS ${_SHA3_AVX512VL_LOW_OBJS} $<TARGET_OBJECTS:sha3_avx512vl_low>)
endif()

set(SHA3_AVX512VL_LOW_OBJS ${_SHA3_AVX512VL_LOW_OBJS} PARENT_SCOPE)

