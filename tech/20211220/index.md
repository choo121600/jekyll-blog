---
layout: post
type: tech
date: 2021-12-20 09:56
category: React
title: 'Switch' was not found in 'react-router-dom' 에러
tech-header: true
hash-tag: [React, WEB]
---


react-router-dom이 버전 6으로 업그레이드 되면서, Switch를 더 이상 지원을 안하게 되었다.

기존의 Switch는 Routes로 바뀌었다.

이는 공식문서를 참조하면 간단하게 해결할 수 있다.

<pre>
    <code>
        import React from 'react';
        import { 
            BrowserRouter, 
            Routes, 
            Route
        } from 'react-router-dom';
        import './App.css';

        import Home from "./pages/home";
        import SignUp from './pages/signup';

        function App() {
            return (
                <BrowserRouter>
                <Routes>
                    <Route path="/" element={<Home />} />
                    <Route path="/signup" element={<SignUp />} />
                </Routes>
                </BrowserRouter>
            );
        }
    </code>
</pre>