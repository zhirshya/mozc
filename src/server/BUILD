# -*- coding: utf-8 -*-
# Copyright 2010-2020, Google Inc.
# All rights reserved.
#
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions are
# met:
#
#     * Redistributions of source code must retain the above copyright
# notice, this list of conditions and the following disclaimer.
#     * Redistributions in binary form must reproduce the above
# copyright notice, this list of conditions and the following disclaimer
# in the documentation and/or other materials provided with the
# distribution.
#     * Neither the name of Google Inc. nor the names of its
# contributors may be used to endorse or promote products derived from
# this software without specific prior written permission.
#
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
# "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
# LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
# A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
# OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
# SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
# LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
# DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
# THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
# (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
# OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

load(
    "//:build_defs.bzl",
    "cc_binary_mozc",
)

package(default_visibility = ["//:__subpackages__"])

# -*- mode: python; -*-
cc_binary_mozc(
    name = "mozc_server",
    srcs = [
        "mozc_server.cc",
        "mozc_server.h",
        "mozc_server_main.cc",
    ],
    copts = ["$(STACK_FRAME_UNLIMITED)"],  # mozc_server.cc
    deps = [
        "//base",
        "//base:crash_report_handler",
        "//base:flags",
        "//base:init_mozc",
        "//base:logging",
        "//base:port",
        "//base:process_mutex",
        "//base:run_level",
        "//base:singleton",
        "//base:system_util",
        "//base:util",
        "//base:winmain",
        "//config:stats_config_util",
        "//session",
        "//session:session_server",
    ],
)

cc_binary_mozc(
    name = "mozc_rpc_server_main",
    srcs = ["mozc_rpc_server_main.cc"],
    deps = [
        "//base",
        "//base:flags",
        "//base:init_mozc",
        "//base:singleton",
        "//base:system_util",
        "//engine:engine_factory",
        "//protocol:commands_proto",
        "//session",
        "//session:random_keyevents_generator",
        "//session:session_handler",
        "//session:session_usage_observer",
    ],
)