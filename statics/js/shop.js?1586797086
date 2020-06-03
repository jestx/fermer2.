function Shop() {
    function t() {
        var t = this,
            a = {};
        t.items = {};
        var e = [];
        t.set = function(a, s) {
            t.items[a] = s, s || (delete t.items[a], e.splice(e.indexOf(a), 1)), $(".cart-button").addClass("pulse").find(".items-count").text(0 == t.count() ? "" : t.count()), setTimeout(function() {
                $(".cart-button").removeClass("pulse")
            }, 750)
        }, t.add = function(a) {
            t.contains(a) || e.push(a), t.set(a, t.contains(a) ? t.countOf(a) + 1 : 1)
        }, t.remove = function(a) {
            t.set(a, t.countOf(a) - 1)
        }, t.countOf = function(a) {
            return t.items[a]
        }, t.contains = function(a) {
            return t.items.hasOwnProperty(a)
        }, t.count = function() {
            return t.getList().length
        }, t.getList = function() {
            return Object.keys(t.items)
        }, t.total = function() {
            var e = t.getList().reduce(function(e, s) {
                var n = y.items.list[s],
                    i = n.cost;
                return 2 == n.type ? e + parseInt($("input[name=user_fields\\[" + n.id + "\\]\\[amount\\]]").val() || 0, 10) : (a.getCouponData && a.getCouponData.hasOwnProperty(s) && (i -= Math.floor(i / 100 * a.getCouponData[s])), e + i * t.countOf(s))
            }, 0);
            return y.currency.format(e)
        }, t.open = function() {
            function s() {
                var t = $(".steam-profile");
                t.find(".avatar").css("background-image", "url(" + a.getSteamProfile.avatar + ")"), t.find(".steamid").text(a.getSteamProfile.steamid)
            }

            function n() {
                $(".total-cost-value").text(t.total()), $(".js-cart-items-area").html(""), e.map(function(t) {
                    o(t), $(".js-buy-form .input input").off().on({
                        invalid: function(t) {
                            t.preventDefault(), $(this).parents(".input").addClass("input_invalid");
                            var a = $(this).parents(".js-buy-form").find("button");
                            a.addClass("shake"), setTimeout(function() {
                                a.removeClass("shake")
                            }, 750)
                        },
                        input: function() {
                            $(this).trigger("update_data")
                        },
                        update_data: function() {
                            var t = $(this).attr("name");
                            if (t && -1 != t.search(/user_fields\[(.*)\]\[(.*)\]/)) {
                                t = t.match(/user_fields\[(.*)\]\[(.*)\]/);
                                for (var a = 0; a < y.items.list[t[1]].fields.length; a++)
                                    if (y.items.list[t[1]].fields[a].id == t[2]) {
                                        y.items.list[t[1]].fields[a].value = $(this).val().trim();
                                        break
                                    }
                            }
                        }
                    }), $(".js-currency input").trigger("input");
                    var a = y.items.list[t].shop_id; - 1 == r.indexOf(a) && r.push(a)
                })
            }

            function i(a, e, s) {
                return null == l && (l = t.getList().some(function(t) {
                    var a = y.items.data[y.items.list[t].shop_id];
                    if (a.length > 1 || 0 != a[0].id) return !0
                })), '        \t        \t<div class="item">                            <div class="image" style="background-image:url(' + a.image + ')"></div>                            <div class="content">                                <div class="sub-text">' + (l ? ' <i class="tag icon"></i>' + a.category.name : "") + '</div>                                <div class="name">' + a.name + '</div>                                <div class="cost">' + e + '</div>                                <div class="actions" data-id="' + a.id + '">' + s + "</div>                            </div>                        </div>"
            }

            function o(e) {
                var s = y.items.list[e],
                    n = s.cost;
                a.surcharge.hasOwnProperty(e) ? n = a.surcharge[e] : a.getCouponData && a.getCouponData.hasOwnProperty(e) && (2 == s.type ? n -= n / 100 * a.getCouponData[e] : n -= Math.floor(n / 100 * a.getCouponData[e]));
                var o = '<span class="change-cost">' + y.currency.format(n * (2 == s.type ? 1 : t.countOf(e))) + "</span>";
                n != s.cost && (o += ' <span class="old-cost">' + y.currency.format(s.cost * (2 == s.type ? 1 : t.countOf(e))) + "</span>"), 2 == s.type && (o += " Р·Р° " + y.currency.prepareSum(s.game_currency_rate, !0) + " РµРґ.");
                var r = "";
                switch (s.fields && s.fields.forEach(function(t) {
                    if ("amount" == t.id) return void(r += '        \t\t\t            \t<div class="field field__exchange js-currency">        \t\t\t                    <div class="input">        \t\t\t                    \t<label>        \t\t\t                    \t\t<input required name="user_fields[' + s.id + "][" + t.id + ']" class="js-currency__amount" value="' + (t.value || s.cost) + '" pattern="\\d*">        \t\t\t                    \t\t<span>' + t.placeholder + '</span>        \t\t\t                    \t</label>        \t\t\t                \t</div>        \t\t\t                \t<i class="exchange icon"></i>        \t\t\t                \t<div class="input">        \t\t\t                    \t<label>        \t\t\t                    \t\t<input class="js-currency__count" value="" pattern="\\d*">        \t\t\t                    \t\t<span>РљРѕР»РёС‡РµСЃС‚РІРѕ</span>        \t\t\t                    \t</label>        \t\t\t                \t</div>        \t\t                \t</div>');
                    r += '        \t\t            \t<div class="field">        \t\t                    <div class="input">        \t\t                    \t<label>        \t\t                    \t\t<input required name="user_fields[' + s.id + "][" + t.id + ']" maxlength="64" value="' + (t.value || "") + '">        \t\t                    \t\t<span>' + t.placeholder + "</span>        \t\t                    \t</label>        \t\t                \t</div>        \t                \t</div>"
                }), s.type) {
                    case 0:
                        r += '        \t\t                <span class="button action icon-only change-count minus"><i class="' + (t.countOf(e) > 1 ? "minus" : "trash alternate") + ' icon"></i></span>        \t\t                <span class="button action icon-only change-count plus ' + (t.countOf(e) >= 100 ? "disabled" : "") + '"><i class="plus icon"></i></span>        \t\t                <span class="counter"><span class="total-count-value">' + t.countOf(e) + "</span> С€С‚.</span>";
                        break;
                    default:
                        r += '        \t\t        \t\t<span class="button action icon-only js-remove-item-from-cart"><i class="trash alternate icon"></i></span>'
                }
                $(".js-cart-items-area").append(i(s, o, r))
            }
            var r = [];
            a.surcharge = {};
            var c = '                \t<form class="cart js-buy-form">                        <div class="items">                            <h2>РљРѕСЂР·РёРЅР°</h2>                            <div class="js-cart-items-area"></div>                            <div class="popular-items-area">                                <h2>РЎ СЌС‚РёРј РІС‹Р±РёСЂР°СЋС‚</h2>                                <div class="popular-items"></div>                            </div>                        </div>                        <div class="form">                            <div class="total-cost">                                <div class="sub-text">РС‚РѕРіРѕ:</div>                                <div class="value total-cost-value"></div>                            </div>                            <div class="form-notice">' + p.formatText(w.cart.form.notice) + '</div>                            <p>Р”Р»СЏ РїСЂРѕРґРѕР»Р¶РµРЅРёСЏ Р·Р°РїРѕР»РЅРёС‚Рµ С„РѕСЂРјСѓ РЅРёР¶Рµ:</p>                            <div class="js-buyer-area">                            \t<div class="field">        \t                    \t<div class="input">        \t\t\t\t            \t<label>        \t\t\t\t            \t\t<input required name="buyer">        \t\t\t\t            \t\t<span>' + w.cart.form.placeholders.nickname + '</span>        \t\t\t\t            \t</label>        \t\t\t\t        \t</div>        \t\t\t        \t</div>                            </div>                            <div class="field">        \t                    <div class="input">        \t                    \t<label>        \t                    \t\t<input name="coupon">        \t                    \t\t<span>РљСѓРїРѕРЅ РЅР° СЃРєРёРґРєСѓ</span>        \t                    \t</label>        \t            \t\t\t<div class="input__ui">        \t            \t\t\t\t<span class="link js-apply-coupon" data-active="РЈРґР°Р»РёС‚СЊ">РџСЂРёРјРµРЅРёС‚СЊ</span>        \t            \t\t\t</div>        \t                \t</div>        \t                \t<small>Р•СЃР»Рё Сѓ РІР°СЃ РµСЃС‚СЊ РєСѓРїРѕРЅ РЅР° СЃРєРёРґРєСѓ, С‚Рѕ РІС‹ РјРѕР¶РµС‚Рµ РІРІРµСЃС‚Рё РµРіРѕ РІ РґР°РЅРЅРѕРµ РїРѕР»Рµ</small>                        \t</div>                            <div class="actions">                                <button class="button themed-button animate" type="submit">РџСЂРѕРґРѕР»Р¶РёС‚СЊ</button>                            </div>                        </div>                    </form>';
            $(".cart-button").addClass("zoomOut"), setTimeout(function() {
                $(".cart-button").removeClass("zoomOut").hide()
            }, 500), C.show({
                content: c,
                onClose: function() {
                    $(".cart-button").addClass("zoomIn").show(), setTimeout(function() {
                        $(".cart-button").removeClass("zoomIn")
                    }, 50)
                }
            }), n(), w.steamAuth && ($(".js-buyer-area").html('        \t\t        <input name="buyer" type="hidden" value="' + k.get("tmc_steamid64") + '">        \t        \t<div class="steam-profile">        \t\t            <div class="avatar"></div>        \t\t            <div class="steamid"><div class="preloader-pulse dark"></div></div>        \t\t            <div class="link auth-in-steam">Р­С‚Рѕ РЅРµ РІС‹?</div>        \t            </div>'), a.getSteamProfile ? s() : _.data.getSteamProfile({
                data: {
                    steamid64: k.get("tmc_steamid64")
                },
                callback: function(t) {
                    if (t.error) return void $(".steam-profile").remove();
                    a.getSteamProfile = t.response, s()
                }
            }));
            w.cart.showRecommendations && _.data.getPopularItems({
                data: {
                    shops: r.join(","),
                    exclude: t.getList().join(",")
                },
                callback: function(a) {
                    a.error || 0 == a.response.length || ($(".popular-items-area").show(), a.response.forEach(function(t) {
                        var a = y.items.list[t],
                            e = y.currency.format(a.cost) + (a.sale ? ' <span class="old-cost">' + y.currency.format(a.sale.old_cost) + "</span>" : "");
                        $(".popular-items").append(i(a, e, '        \t                    \t\t<span class="button action js-add-popular-item">                                        \t<span class="label"><i class="shopping basket icon"></i></span>                                        \tР”РѕР±Р°РІРёС‚СЊ                                        </span>'))
                    }), $(".js-add-popular-item").off().on("click", function() {
                        var a = $(this).parents("[data-id]").attr("data-id");
                        t.add(a), n(), $(this).parents(".item").remove(), 0 == $(".popular-items").children().length && $(".popular-items-area").hide()
                    }))
                }
            }), $(".js-apply-coupon").off().on("click", function() {
                function t() {
                    i.val(a.getCouponData.coupon).attr("value", i.val()).trigger("disable"), e.addClass("js-remove").attr("data-active", e.text()).text(s), n()
                }
                var e = $(this),
                    s = e.attr("data-active"),
                    i = e.parents(".input").find("input");
                if (e.hasClass("js-remove")) return i.val("").attr("value", "").trigger("enable"), e.removeClass("js-remove").attr("data-active", e.text()).text(s), delete a.getCouponData, void n();
                if (a.getCouponData) t();
                else {
                    var o = i.val().trim();
                    if (!o) return void i.focus();
                    _.data.getCouponData({
                        data: {
                            coupon: o,
                            shops: r.join(",")
                        },
                        callback: function(e) {
                            if (e.error) return y.message.error(e.error.message), void i.focus();
                            a.getCouponData = e.response, a.getCouponData.coupon = o, t()
                        }
                    })
                }
            }), a.getCouponData && $(".js-apply-coupon").click(), p.bindForm(".js-buy-form", {
                api: "shop",
                action: "buyItems",
                appendParams: {
                    domain: w.domain
                },
                callbackBefore: function(a, e) {
                    e.items = t.getList().reduce(function(a, e) {
                        return a.push(e + ":" + (2 == y.items.list[e].type ? 1 : t.items[e])), a
                    }, [])
                },
                callbackAfter: function(t, e) {
                    if (!e.surcharge) return void y.sci.open(e.cart_id);
                    a.surcharge = e.surcharge, n(), t.find(".form").find(".actions").html('<div class="button themed-button js-open-pay-window">РџРµСЂРµР№С‚Рё Рє РѕРїР»Р°С‚Рµ</div>'), t.find(".input input").trigger("disable"), $(".modal").find(".range input").attr("disabled", !0), $(".modal").find(".button.action").addClass("disabled"), $(".total-cost-value").text(y.currency.format(e.total));
                    var s = Object.keys(a.surcharge).reduce(function(t, a) {
                            return t.push("<strong>" + y.items.list[a].name + "</strong>"), t
                        }, []),
                        i = "Р‘СѓРґРµС‚ РїСЂРѕРёР·РІРµРґРµРЅР° СЃРєРёРґРєР° СЃ СѓС‡РµС‚РѕРј РґРѕРїР»Р°С‚С‹ РЅР° С‚РѕРІР°СЂ" + (s.length > 1 ? "С‹" : "") + " " + s.join(", ");
                    t.find(".form").find(".actions").append('<div class="surcharge-info">' + i + "</div>"), $(".js-open-pay-window").off().on("click", function() {
                        $(this).addClass("load"), y.sci.open(e.cart_id)
                    })
                }
            });
            var l = null
        }, $("body").on("click", ".open-cart", function() {
            if (t.count() > 0) return void t.open();
            var a = $(this);
            a.addClass("shake"), setTimeout(function() {
                a.removeClass("shake")
            }, 750)
        });
        var s;
        $("body").on(h() ? "touchend" : "mouseup", ".change-count", function() {
            clearTimeout(s)
        }).on(h() ? "touchstart" : "mousedown", ".change-count", function() {
            var e = $(this),
                n = 200;
            ! function i() {
                function o() {
                    s = setTimeout(function() {
                        i()
                    }, n), n = n > 20 ? n - 20 : n
                }
                $(".change-count").removeClass("disabled");
                var r = e.parent().attr("data-id");
                if (e.hasClass("plus")) t.add(r), e.parent().find(".minus").find(".icon").removeClass("trash alternate").addClass("minus"), t.countOf(r) >= 100 ? e.addClass("disabled") : o();
                else if (t.remove(r), t.contains(r)) 1 == t.countOf(r) ? e.find(".icon").removeClass("minus").addClass("trash alternate") : o();
                else if (e.parents(".item").remove(), 0 == t.count()) return void C.hide();
                var c = y.items.list[r].cost;
                a.getCouponData && a.getCouponData.hasOwnProperty(r) && (e.parents(".item").find(".old-cost").text(y.currency.format(c * t.countOf(r))), c -= Math.floor(c / 100 * a.getCouponData[r])), e.parents(".item").find(".change-cost").text(y.currency.format(c * t.countOf(r))), e.parent().find(".total-count-value").text(t.countOf(r)), $(".total-cost-value").text(t.total())
            }()
        }), $("body").on("input", ".js-currency input", function() {
            function e(t, a) {
                a = Math.floor(a) || "", t.val(a).attr("value", a).trigger("update_data")
            }
            var s = y.items.list[$(this).parents("[data-id]").attr("data-id")],
                n = $(this).val().replace(/[^0-9]/gi, "");
            e($(this), n);
            var i, o, r = s.cost;
            if (a.getCouponData && a.getCouponData.hasOwnProperty(s.id) && (r -= r / 100 * a.getCouponData[s.id]), $(this).hasClass("js-currency__amount") ? (i = n, o = i / r * s.game_currency_rate, e($(this).parents(".js-currency").find(".js-currency__count"), o)) : (o = n, i = Math.ceil(o / s.game_currency_rate * r), e($(this).parents(".js-currency").find(".js-currency__amount"), i)), i > 1e4) return e($(this).parents(".js-currency").find(".js-currency__amount"), 1e4), void $(this).parents(".js-currency").find(".js-currency__amount").trigger("input");
            $(".total-cost-value").text(t.total())
        }), $("body").on("click", ".js-remove-item-from-cart", function() {
            var a = $(this).parents("[data-id]").attr("data-id");
            if (t.set(a, 0), 0 == t.count()) return void C.hide();
            $(this).parents(".item").remove(), $(".total-cost-value").text(t.total())
        })
    }

    function a() {
        function t() {
            var t = $("header");
            return t.height() > t.width()
        }
        this.setFSS = function() {
            $(".cover__effect").html('<div id="background-output"></div>'), g("libs/fss/fss.js?3", function() {
                var t = document.createElement("canvas");
                t.getContext && t.getContext("2d") && initBackground(".cover__effect", {
                    background: {
                        enabled: !0,
                        RENDER: {
                            renderer: "canvas"
                        },
                        MESH: {
                            ambient: "#333333",
                            diffuse: "#555555",
                            width: 1.2,
                            height: 1.2,
                            depth: 10,
                            segments: Math.round($("header").width() / 100),
                            slices: Math.round($("header").height() / 100),
                            xRange: .2,
                            yRange: .2,
                            zRange: 1,
                            speed: 5e-4
                        },
                        LIGHT: {
                            autopilot: !0,
                            ambient: "#888888",
                            diffuse: "#ffffff",
                            count: 2,
                            zOffset: 100,
                            xyScalar: 1,
                            speed: .001,
                            gravity: 1200,
                            dampening: .15,
                            minLimit: 8,
                            maxLimit: null,
                            minDistance: 20,
                            maxDistance: 400,
                            draw: !1
                        }
                    }
                })
            })
        }, this.setParticles = function() {
            $(".cover__effect").html('<div id="particles-js"></div>'), g("libs/particles/particles.min.js", function() {
                particlesJS("particles-js", {
                    particles: {
                        number: {
                            value: t() ? 80 : 220,
                            density: {
                                enable: !1,
                                value_area: 800
                            }
                        },
                        color: {
                            value: "#ffffff"
                        },
                        shape: {
                            type: "circle",
                            stroke: {
                                width: 0,
                                color: "#000000"
                            },
                            polygon: {
                                nb_sides: 5
                            },
                            image: {
                                src: "img/github.svg",
                                width: 100,
                                height: 100
                            }
                        },
                        opacity: {
                            value: 1,
                            random: !1,
                            anim: {
                                enable: !1,
                                speed: 1,
                                opacity_min: .1,
                                sync: !1
                            }
                        },
                        size: {
                            value: 3,
                            random: !0,
                            anim: {
                                enable: !1,
                                speed: 80,
                                size_min: .1,
                                sync: !1
                            }
                        },
                        line_linked: {
                            enable: !1,
                            distance: 100,
                            color: "#ffffff",
                            opacity: .4,
                            width: 1
                        },
                        move: {
                            enable: !0,
                            speed: 1,
                            direction: "none",
                            random: !1,
                            straight: !1,
                            out_mode: "out",
                            bounce: !1,
                            attract: {
                                enable: !1,
                                rotateX: 600,
                                rotateY: 1200
                            }
                        }
                    },
                    interactivity: {
                        detect_on: "canvas",
                        events: {
                            onhover: {
                                enable: !1,
                                mode: "repulse"
                            },
                            onclick: {
                                enable: !1,
                                mode: "push"
                            },
                            resize: !0
                        },
                        modes: {
                            grab: {
                                distance: 800,
                                line_linked: {
                                    opacity: 1
                                }
                            },
                            bubble: {
                                distance: 800,
                                size: 80,
                                duration: 2,
                                opacity: .8,
                                speed: 3
                            },
                            repulse: {
                                distance: 400,
                                duration: .4
                            },
                            push: {
                                particles_nb: 4
                            },
                            remove: {
                                particles_nb: 2
                            }
                        }
                    },
                    retina_detect: !0
                })
            })
        }, this.setVideo = function(t) {
            $(".cover__effect").html('<div id="yt-background"><div id="player"></div></div>'), g("libs/yt-background/yt-background.js?20", function() {
                new YTBackground({
                    isMobile: h(),
                    videoID: t
                })
            })
        }
    }

    function e() {
        function t() {
            k.set("tmc_currency", s, {
                expires: 31536e3
            })
        }
        var a, e = this,
            s = "RUB";
        e.init = function(e) {
            a = e;
            var n = k.get("tmc_currency");
            n && a.hasOwnProperty(n) && (s = n, t())
        }, e.set = function(e) {
            a.hasOwnProperty(e) && null != a[e].value && (s = e, y.items.load(), t())
        }, e.get = function() {
            return a[s]
        }, e.format = function(t) {
            return e.prepareSum(t / e.get().value) + " " + e.get().symbol
        }, e.prepareSum = function(t, a) {
            return a ? t.toString().replace(/\d(?=(\d{3})+$)/g, "$& ") : t.toFixed(2).replace(/\d(?=(\d{3})+\.)/g, "$& ")
        }, e.getSymbol = function(t) {
            return t = t.toUpperCase(), a.hasOwnProperty(t) ? a[t].symbol : t
        }
    }

    function s() {
        var t = this,
            a = null;
        t.list = {}, t.data = {}, t.load = function(e) {
            function s(a) {
                var e = t.data[a];
                if (!e.length) return void $("#items .preloader").html('                            <div class="empty"></div>                            <p>РўРѕРІР°СЂС‹ РµС‰Рµ РЅРµ СЃРѕР·РґР°РЅС‹</p>');
                var s = "",
                    n = e.length > 1 || 0 != e[0].id ? '                        \t<span class="button action active" data-category-select="-1">        \t                \t<span class="label"><i class="tags icon"></i></span>        \t                \tР’СЃРµ С‚РѕРІР°СЂС‹        \t                </span>' : "";
                e.forEach(function(e) {
                    n && (n += '        \t                \t<span class="button action" data-category-select="' + e.id + '">        \t                \t\t<span class="label"><i class="tag icon"></i></span>        \t                \t\t' + e.name + "        \t                \t</span>"), e.items.forEach(function(i) {
                        i.shop_id = a, i.category = {
                            id: e.id,
                            name: e.name
                        }, t.list[i.id] = i;
                        var o = "";
                        if (i.sale) {
                            var r = "";
                            i.sale.until && (r = '<div class="sale__timer" data-timer="' + i.sale.until + '"><div class="preloader-pulse dark"></div></div>', p.salesTimer()), o = '        \t\t                    <div class="sale">        \t\t                    \t<div class="sale__size">-' + i.sale.percent + "%</div>        \t\t                    \t" + r + "        \t\t                    </div>"
                        }
                        s += '                                <div class="card animate" data-category-id="' + e.id + '" data-item-id="' + i.id + '">                            \t    <div class="image" style="background-image:url(' + i.image + ')"></div>                                    <div class="description">                                        ' + o + '                                        <div class="sub-text">' + (n ? ' <i class="tag icon"></i>' + e.name : "") + '</div>                                        <div class="name">' + i.name + '</div>                                        <div class="cost">' + y.currency.format(i.cost) + (i.sale ? ' <span class="old-cost">' + y.currency.format(i.sale.old_cost) + "</span>" : "") + (2 == i.type ? " Р·Р° " + y.currency.prepareSum(i.game_currency_rate, !0) + " РµРґ." : "") + "</div>                                    </div>                                </div>"
                    })
                }), $(".categories").html(n), $("#items").html(s), $("[data-category-select]").off().on("click", function() {
                    var t = $(this).attr("data-category-select");
                    $("[data-category-select]").removeClass("active"), $(this).addClass("active");
                    var a = [],
                        e = [];
                    $("[data-category-id]").each(function() {
                        var s = $(this);
                        if (s.attr("data-category-id") != t && -1 != t) return void a.push(s);
                        "none" == s.css("display") && e.push(s)
                    }), a.forEach(function(t) {
                        t.addClass("zoomOut")
                    }), setTimeout(function() {
                        a.forEach(function(t) {
                            t.removeClass("zoomOut").hide()
                        }), e.forEach(function(t) {
                            t.show().addClass("zoomIn")
                        }), setTimeout(function() {
                            e.forEach(function(t) {
                                t.removeClass("zoomIn")
                            })
                        }, 1e3)
                    }, a.length ? 375 : 0)
                }), $("[data-item-id]").off().on("click", function() {
                    function a() {
                        var t = $(".js-add-to-cart");
                        t.removeClass("js-add-to-cart").off().text("Рљ РєРѕСЂР·РёРЅРµ").after(' <div class="button flat modal-close">Р’С‹Р±СЂР°С‚СЊ РµС‰Рµ</div>'), setTimeout(function() {
                            t.addClass("open-cart")
                        }, 0)
                    }
                    var e = $(this).attr("data-item-id"),
                        s = t.list[e];
                    C.show({
                        content: '        \t                    <div class="item">        \t                        <div class="image" style="background-image:url(' + s.image + ')"></div>        \t                        <div class="content">        \t                        \t<div class="content__area">        \t\t                            <div class="sub-text">' + (n ? ' <i class="tag icon"></i>' + s.category.name : "") + '</div>        \t\t                            <div class="name">' + s.name + '</div>        \t\t                            <div class="cost">' + y.currency.format(s.cost) + (s.sale ? ' <span class="old-cost">' + y.currency.format(s.sale.old_cost) + "</span>" : "") + (2 == s.type ? " Р·Р° " + y.currency.prepareSum(s.game_currency_rate, !0) + " РµРґ." : "") + '</div>        \t\t                            <div class="js-add-to-cart button themed-button">Р”РѕР±Р°РІРёС‚СЊ РІ РєРѕСЂР·РёРЅСѓ</div>        \t\t                            <div class="description">' + p.formatText(s.description) + "</div>        \t                            </div>        \t                        </div>        \t                    </div>"
                    }), y.cart.contains(e) ? a() : $(".js-add-to-cart").on("click", function() {
                        if (w.steamAuth && !k.get("tmc_steamid64")) return void y.page.show("РќРµРѕР±С…РѕРґРёРјР° Р°РІС‚РѕСЂРёР·Р°С†РёСЏ", '                                        РџРѕР¶Р°Р»СѓР№СЃС‚Р°, Р°РІС‚РѕСЂРёР·СѓР№С‚РµСЃСЊ СЃ РїРѕРјРѕС‰СЊСЋ Steam, С‡С‚РѕР±С‹ РґРѕР±Р°РІРёС‚СЊ СЌС‚РѕС‚ С‚РѕРІР°СЂ РІ РєРѕСЂР·РёРЅСѓ.                                        <div class="steam-auth">                                            <span class="button themed-button auth-in-steam">Р’РѕР№С‚Рё С‡РµСЂРµР· <i class="steam icon"></i> Steam</span>                                        </div>');
                        y.cart.add(e), a()
                    })
                })
            }
            return $(".categories").html(""), $("#items").html('<div class="preloader"></div>'), a || e ? (e ? a = e : e = a, $("#items .preloader").html('                    <div class="load"><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div></div>'), t.data.hasOwnProperty(e) ? void s(e) : void _.shop.getItems({
                data: {
                    shop: e
                },
                callback: function(a) {
                    t.data[e] = a.error ? [] : a.response.categories, s(e)
                }
            })) : void $("#items .preloader").html('                        <div class="need-choose"></div>                        <p>Р’С‹Р±РµСЂРёС‚Рµ СЃРµСЂРІРµСЂ, С‡С‚РѕР±С‹ РѕС‚РѕР±СЂР°Р·РёС‚СЊ СЃРїРёСЃРѕРє С‚РѕРІР°СЂРѕРІ</p>')
        }
    }

    function n() {
        function t(t, e) {
            clearTimeout(a), s.removeClass("success error process").fadeIn(n).addClass(e).html(t);
            var i = 1e3 * Math.ceil(t.length / 20);
            a = setTimeout(function() {
                s.fadeOut(n)
            }, i)
        }
        var a, e = this,
            s = $(".message"),
            n = 100;
        e.success = function(a) {
            t(a, "success")
        }, e.error = function(a) {
            t(a, "error")
        }, e.process = function(a) {
            t(a, "process")
        }
    }

    function i() {
        var t = null,
            a = null;
        this.show = function(e) {
            $(".modal").removeClass("small black");
            var s = $(window).width() > 480 ? "zoomIn" : "fadeInUp";
            e.isSmall && $(".modal").addClass("small"), e.isBlack && $(".modal").addClass("black"), $(".modal").show().find(".content").scrollTop(0).addClass(s).html(e.content), null == a && (a = $(document).scrollTop(), $("body").addClass("disable-scroll").css("margin-top", "-" + a + "px")), setTimeout(function() {
                $(".modal").find(".content").removeClass(s)
            }, 500), t = t || e.onClose || null
        }, this.hide = function() {
            var e = $(window).width() > 480 ? "zoomOut" : "fadeOutDown";
            $(".modal").find(".content").addClass(e), setTimeout(function() {
                $(".modal").hide().find(".content").removeClass(e).html(""), $("body").removeClass("disable-scroll").css("margin-top", ""), $(window).scrollTop(a), a = null
            }, 50), t && (t(), t = null)
        }, $("body").on(h() ? "touchend" : "click", ".modal-close", this.hide)
    }

    function o() {
        this.manual = function(t, a, e) {
            var s = e ? '                \t<div class="video-area">        \t        \t<div class="video" style="background-image: url(https://i.ytimg.com/vi/' + e + '/maxresdefault.jpg)">        \t        \t\t<svg width="68" height="48" viewBox="0 0 68 48">        \t        \t\t\t<path class="yt-button-shape" d="M66.52,7.74c-0.78-2.93-2.49-5.41-5.42-6.19C55.79,.13,34,0,34,0S12.21,.13,6.9,1.55 C3.97,2.33,2.27,4.81,1.48,7.74C0.06,13.05,0,24,0,24s0.06,10.95,1.48,16.26c0.78,2.93,2.49,5.41,5.42,6.19 C12.21,47.87,34,48,34,48s21.79-0.13,27.1-1.55c2.93-0.78,4.64-3.26,5.42-6.19C67.94,34.95,68,24,68,24S67.94,13.05,66.52,7.74z"></path>        \t        \t\t\t<path class="yt-button-icon" d="M 45,24 27,14 27,34"></path>        \t        \t\t</svg>        \t        \t</div>                \t</div>' : "";
            $(".module-manual").html('                    <h2 class="enable-padding">' + t + '</h2>                    <div class="manual clear-fix">                        <div class="content">' + p.formatText(a) + "</div>                        " + s + "                    </div>"), $(".video").on("click", function() {
                C.show({
                    isBlack: !0,
                    content: '<div class="video"><iframe src="//www.youtube.com/embed/' + e + '?autoplay=1&showinfo=0" frameborder="0" allowfullscreen></iframe></div>'
                })
            })
        }, this.lastPurchases = function(t, a) {
            _.shop.getLastPurchases({
                data: {
                    shops: t,
                    count: 10
                },
                callback: function(t) {
                    if (!t.error && 0 != t.response.length) {
                        var e = ".module-last-purchases",
                            s = t.response,
                            n = "";
                        s.forEach(function(t) {
                            n += '                                <div class="card">                            \t    <div class="image" style="background-image:url(' + t.item.image + ')"></div>                                    <div class="description">                                        <div class="sub-text">' + (a ? t.buyer : "") + '</div>                                        <div class="name">' + t.item.name + "</div>                                    </div>                                </div>"
                        }), $(e).html('                            <div class="white-area">                            \t<div class="wrapper">                                \t<h2>                                \t\tРџРѕСЃР»РµРґРЅРёРµ РїРѕРєСѓРїРєРё                                \t\t<span class="sub-text">РџРѕСЃР»РµРґРЅРёРµ С‚РѕРІР°СЂС‹, РїСЂРёРѕР±СЂРµС‚РµРЅРЅС‹Рµ РїРѕР»СЊР·РѕРІР°С‚РµР»СЏРјРё РІ РјР°РіР°Р·РёРЅРµ</span>                                \t</h2>                                \t<div class="cards small clear-fix">                                \t    <div class="overwrap-area">' + n + "</div>                                \t</div>                            \t</div>                        \t</div>"), s.length > 5 && setInterval(function() {
                            var t = $(e).find(".card").first();
                            t.css("margin-left", "-20%"), setTimeout(function() {
                                $(e).find(".overwrap-area").append(t), t.css("margin-left", "")
                            }, 1e3)
                        }, 3e3)
                    }
                }
            })
        }
    }

    function r() {
        this.init = function(t) {
            var a = $(".module-monitoring");
            a.html('<div class="preloader-pulse"></div>'), _.shop.getOnline({
                data: {
                    shop: w.shopID
                },
                callback: function(e) {
                    var s = "РЎРµСЂРІРµСЂ РЅРµРґРѕСЃС‚СѓРїРµРЅ";
                    e.response && (s = t.replace(/{players}/g, e.response.players).replace(/{max_players}/g, e.response.max_players).replace(/{version}/g, e.response.version)), a.text(s)
                }
            })
        }, this.init2 = function(t, a) {
            var e = "";
            t.forEach(function(t) {
                var s = t.server_address ? '        \t\t\t    <div class="button action" data-to-clipboard="' + t.server_address + '">        \t\t        \t<span class="label"><i class="play icon"></i></span>        \t\t        \t' + t.server_address + "        \t\t        </div>" : "";
                e += '        \t\t\t    <div class="progress-bar" data-monitoring="' + t.id + '">        \t\t        \t<div class="label">        \t\t\t        \t<div class="shop-name">' + t.name + "</div>        \t\t\t        \t" + s + '        \t\t\t        </div>        \t\t        \t<div class="bar loading">        \t\t\t        \t<div class="fill"></div>        \t\t        \t</div>        \t\t        \t<div class="server-info"><div class="preloader-pulse dark"></div></div>        \t        \t</div>', _.shop.getOnline({
                    data: {
                        shop: t.id
                    },
                    callback: function(e) {
                        var s = $("[data-monitoring=" + t.id + "]");
                        if (s.find(".bar").removeClass("loading"), e.error) return s.find(".server-info").text("РЎРµСЂРІРµСЂ РЅРµРґРѕСЃС‚СѓРїРµРЅ"), void s.find(".bar").addClass("error");
                        s.find(".server-info").text(a.replace(/{players}/g, e.response.players).replace(/{max_players}/g, e.response.max_players).replace(/{version}/g, e.response.version)), s.find(".fill").css("width", e.response.players / e.response.max_players * 100 + "%")
                    }
                })
            }), e = '        \t    \t<div class="white-area">                    \t<div class="wrapper">        \t            \t<div class="bars">' + e + "</div>                    \t</div>                \t</div>", $(".module-servers-monitoring").html(e)
        }
    }

    function c() {
        function t(t) {
            var a, e, s = 0;
            if (0 === t.length) return s;
            for (a = 0; a < t.length; a++) e = t.charCodeAt(a), s = (s << 5) - s + e, s |= 0;
            return s
        }
        var a = $(".notice");
        this.show = function(e, s, n, i, o) {
            if (n) {
                var r = k.get("tmc_notice");
                if (hash = t(e + s), r == hash) return
            }
            a.find(".title").text(e), a.find(".text").html(p.formatText(s)), i && a.addClass(i), o && a.addClass("top"), a.addClass("show")
        }, $(".notice-close").on("click", function() {
            a.removeClass("show"), "" !== hash && k.set("tmc_notice", hash, {
                expires: 604800
            })
        })
    }

    function l() {
        function t(t) {
            var a = t || window.location.href;
            return a = a.replace(/^https?:\/\//i, "").replace(window.location.hostname, "").replace(/^\//i, "")
        }

        function a(t) {
            return -1 != t.search(/^[a-z0-9_-]{1,64}$/i)
        }
        var e = this;
        e.load = function(t, s) {
            a(t) && _.data.getPage({
                data: {
                    shop: w.shopID,
                    page: t
                },
                callback: function(a) {
                    a = a.response;
                    var n = s ? "replaceState" : "pushState";
                    window.history[n]({}, "", t), e.show(a.title, a.content)
                }
            })
        }, e.show = function(t, a) {
            var e = '                    <div class="page">                        <h2>' + t + "</h2>                        " + p.formatText(a) + "                    </div>";
            C.show({
                content: e,
                isSmall: !(a.length > 500),
                onClose: function() {
                    window.history.pushState({}, "", "/")
                }
            })
        }, $("body").on("click", "a", function(s) {
            s = s || window.event;
            var n = t($(this).attr("href"));
            a(n) && (s.preventDefault(), e.load(n))
        }), $(window).on("popstate", function() {
            e.load(t(), !0)
        }), e.load(t(), !0)
    }

    function d() {
        function t() {
            a.fadeOut("500", function() {
                a.css("width", "")
            })
        }
        var a = $(".progress"),
            e = 0;
        this.start = function() {
            e = 0, a.fadeIn("500");
            var s = setInterval(function() {
                e += 1, a.css("width", e + "%"), e >= 100 && (clearInterval(s), t())
            }, 100)
        }, this.finish = function() {
            e = 100
        }
    }

    function u() {
        this.open = function(t, a) {
            function e() {
                var i = "";
                s.forEach(function(t, a) {
                    var e = "";
                    t.payways.forEach(function(s, n) {
                        e += '        \t                    <div class="way js-payway" data-category-id="' + a + '" data-payway-id="' + n + '">        \t                        <div class="image" style="background-image:url(' + s.image + ')"></div>        \t                        <div class="description">        \t                            <div class="name">' + s.name + '</div>        \t                            <div class="sub-text">' + t.name + "</div>        \t                        </div>        \t                    </div>"
                    }), i += '<div class="ways">' + e + "</div>"
                }), i = '                        <div class="payways">                            <h2>                            \tРћРїР»Р°С‚Р°                            \t<span class="sub-text">Р’С‹Р±РµСЂРёС‚Рµ РїСЂРµРґРїРѕС‡РёС‚Р°РµРјС‹Р№ СЃРїРѕСЃРѕР± РѕРїР»Р°С‚С‹</span>                            </h2>                            ' + i + "                        </div>", a ? $(".sci").html(i) : C.show({
                    content: i
                }), $(".js-payway").off().on("click", function() {
                    function i(e, s) {
                        var n = $(".payway-price");
                        n.html('<div class="preloader-pulse dark"></div>');
                        var i = $(".pay-action").find("button");
                        i.removeClass("disable-switch").prop("disabled", !1), _.payment.getPayData({
                            data: {
                                cart_id: t,
                                type: e
                            },
                            callback: function(o) {
                                if (o.error) return y.message.error(o.error.message), n.text("вЂ”"), void i.addClass("disable-switch").prop("disabled", !0);
                                n.text(y.currency.prepareSum(o.response.price) + " " + y.currency.getSymbol(s));
                                var r = location.protocol + "//" + location.hostname + "/#",
                                    c = {
                                        cart_id: t,
                                        type: e,
                                        success_url: r + "success",
                                        pending_url: r + "pending",
                                        fail_url: r + "fail"
                                    };
                                c = $.extend({}, c, a || {}), p.bindForm(".pay-action", {
                                    api: "payment",
                                    action: "getPayForm",
                                    appendParams: c,
                                    callbackBefore: function(t, a) {
                                        return !a.type
                                    },
                                    callbackAfter: function(t, a) {
                                        if (t.find("button").addClass("load"), a.message) return y.message.success(a.message), console.log(c), void setTimeout(function() {
                                            location.href = c.pending_url, c.pending_url == r + "pending" && location.reload()
                                        }, 5e3);
                                        if (a.form) {
                                            a = a.form;
                                            var e = document.createElement("form");
                                            e.method = a.method, e.action = a.action, e.style.display = "none", $.each(a.params, function(t, a) {
                                                e.innerHTML += '<input type="hidden" name="' + t + '" value="' + a + '">'
                                            }), document.body.appendChild(e), e.submit()
                                        }
                                    }
                                })
                            }
                        })
                    }
                    var o = s[$(this).attr("data-category-id")].payways[$(this).attr("data-payway-id")],
                        r = "",
                        c = "";
                    o.fields && o.fields.forEach(function(t) {
                        r += '        \t\t                \t<div class="input">        \t\t                    \t<label>        \t\t                    \t\t<input name="' + t.name + '" type="' + (t.type ? t.type : "text") + '">        \t\t                    \t\t<span>' + t.label + '</span>        \t\t                    \t</label>        \t\t            \t\t\t<div class="input__ui"></div>        \t\t                \t</div>'
                    }), o.types.length > 1 && (o.types.forEach(function(t) {
                        c += '<span class="button action" data-payway-type="' + t.type + '" data-payway-currency=' + t.currency + ">" + t.currency + "</span> "
                    }), c = '<div class="buttons-group types">' + c + "</div>"), C.show({
                        content: '        \t                    <div class="payway">        \t                        <form class="pay-action">        \t                            <div class="colored-block">        \t                                <h2>        \t                                    ' + o.name + '        \t                                    <span class="sub-text">РћРїР»Р°С‚Р° С‡РµСЂРµР· ' + o.name + '</span>        \t                                </h2>        \t                                <div class="total-cost">        \t                                    <div class="sub-text">РЎСѓРјРјР°:</div>        \t                                    <div class="value payway-price"></div>        \t                                </div>        \t                            </div>        \t                            ' + c + "        \t                            " + r + '        \t                            <label class="checkbox">        \t                                <input type="checkbox" name="agreement" checked>        \t                                <span class="checkbox__box"></span>        \t                                РЇ РїСЂРёРЅРёРјР°СЋ СѓСЃР»РѕРІРёСЏ <a href="' + n + '" target="_blank">РїРѕР»СЊР·РѕРІР°С‚РµР»СЊСЃРєРѕРіРѕ СЃРѕРіР»Р°С€РµРЅРёСЏ</a>        \t                            </label>        \t                            <div class="actions">        \t                                <button class="button themed-button" type="submit">РћРїР»Р°С‚РёС‚СЊ</button>        \t                                ' + (a ? '<div class="button flat modal-close">Р—Р°РєСЂС‹С‚СЊ</div>' : '<div class="button flat show-ways">Р’РµСЂРЅСѓС‚СЊСЃСЏ РЅР°Р·Р°Рґ</div>') + "        \t                            </div>        \t                        </form>        \t                    </div>",
                        isSmall: !0
                    }), o.types.length > 1 ? ($("[data-payway-type]").off().on("click", function() {
                        $("[data-payway-type]").removeClass("active"), $(this).addClass("active"), i($(this).attr("data-payway-type"), $(this).attr("data-payway-currency"))
                    }), $("[data-payway-type]").eq(0).click()) : i(o.types[0].type, o.types[0].currency), $(".show-ways").off().on("click", function() {
                        e()
                    }), $("[name=agreement]").off().on("click", function() {
                        var t = $(".pay-action").find("button");
                        if ($(this).is(":checked") && !t.hasClass("disable-switch")) return void t.prop("disabled", !1);
                        t.prop("disabled", !0)
                    })
                })
            }
            var s, n = "https://pay.trademc.org/agreement.html";
            _.payment.getWays({
                data: {
                    cart_id: t
                },
                callback: function(t) {
                    if (t.error) return void(a ? $(".sci").html('        \t\t\t                <div class="payways">        \t\t\t                    <h2>        \t\t\t                    \tРћС€РёР±РєР°        \t\t\t                    \t<span class="sub-text">' + t.error.message + "</span>        \t\t\t                    </h2>        \t\t\t                </div>") : y.message.error(t.error.message));
                    s = t.response, e()
                }
            })
        }
    }

    function p() {
        $(".dropdown").attr("data-list", function(t, a) {
            var e = JSON.parse($("<div/>").text(a).html()),
                s = $(this).attr("data-placeholder"),
                n = $(this).attr("data-action"),
                i = "";
            if (h()) {
                s && (i += "<option selected disabled>" + s + "</option>");
                for (var o = 0; o < e.length; o++) i += '<option value="' + e[o].value + '">' + e[o].name + "</option>";
                i = '<select onchange="' + n + '(this.value)">' + i + "</select>"
            } else {
                for (var o = 0; o < e.length; o++) i += '<span onclick="' + n + "('" + e[o].value + "')\">" + e[o].name + "</span>";
                i = '<span class="options">' + i + "</span>"
            }
            var r = 0,
                c = $(this).attr("data-default-value");
            if (void 0 != c)
                for (var o = 0; o < e.length; o++)
                    if (e[o].value == c) {
                        r = o;
                        break
                    } $(this).find(".current-value").length || (i = '<span class="current-value">' + e[r].name + "</span>" + i), $(this).append(i)
        }), $(".dropdown").on("mouseover", function() {
            $(this).addClass("show")
        }), $(".dropdown").on("mouseout", function() {
            $(this).removeClass("show")
        }), $(".dropdown .options span").on("click", function() {
            var t = $(this).parents(".dropdown");
            t.find(".current-value").text($(this).text()), t.removeClass("show")
        }), $(".dropdown select").on("change", function() {
            $(this).parents(".dropdown").find(".current-value").text($(this).find(":selected").text())
        }), $(".open-menu").on("click", function() {
            $(this).toggleClass("active"), $("nav").toggleClass("visible")
        }), $("body").on({
            input: function() {
                $(this).parents(".input")[$(this).is(":invalid") ? "addClass" : "removeClass"]("input_invalid"), $(this).attr("value", $(this).val())
            },
            focus: function() {
                $(this).parents(".input").addClass("input_focus")
            },
            blur: function() {
                $(this).parents(".input").removeClass("input_focus")
            },
            disable: function() {
                $(this).prop("readonly", !0).parents(".input").addClass("input_disabled")
            },
            enable: function() {
                $(this).prop("readonly", "").parents(".input").removeClass("input_disabled")
            }
        }, ".input input");
        var t = {
            375: "by",
            994: "az",
            91: "in",
            7: "ru",
            77: "kz",
            380: "ua",
            44: "gb",
            9955: "ge",
            370: "lt",
            992: "tj",
            66: "th",
            998: "uz",
            507: "pa",
            374: "am",
            81: "jp",
            1: "us",
            371: "lv",
            90: "tr",
            373: "md",
            972: "il",
            84: "vn",
            372: "ee",
            82: "kr",
            996: "kg"
        };
        $("body").on("input", "input[type=tel]", function() {
            var a = $(this).val().replace(/[^0-9]/gi, ""),
                e = "",
                s = 0;
            if (a.length)
                for (var n = Object.keys(t), i = 0; i < n.length; i++) {
                    var o = n[i];
                    if (0 === a.indexOf(o.substr(0, a.length)) && (e = '<div class="flag ' + t[o] + '"></div>', s = o.length, a.length == s)) break
                }
            $(this).parents(".input").find(".input__ui").html(e), e || (a = ""), a = a.substr(0, s + 10), a.length && (a = "+" + a), $(this).val(a), $(this).attr("value", a)
        }), $("body").on("click", "[data-to-clipboard]", function() {
            var t = $(this).attr("data-to-clipboard"),
                a = $("<input>");
            $("body").append(a), a.val(t).select(), document.execCommand("copy"), a.remove(), y.message.success("РЎРєРѕРїРёСЂРѕРІР°РЅРѕ РІ Р±СѓС„РµСЂ!")
        }), $(".scroll-to-main").on("click", function() {
            $("html, body").animate({
                scrollTop: $(".module-items").offset().top
            }, 500)
        }), $("body").on("click", ".auth-in-steam", function() {
            window.location.href = "/steam.php"
        });
        var a = {
                success: {
                    title: "РџРѕР·РґСЂР°РІР»СЏРµРј",
                    content: "РћРїР»Р°С‚Р° СѓСЃРїРµС€РЅРѕ СЃРѕРІРµСЂС€РµРЅР°. РўРѕРІР°СЂ Р±СѓРґРµС‚ РІС‹РґР°РЅ РІР°Рј РІ С‚РµС‡РµРЅРёРµ РЅРµСЃРєРѕР»СЊРєРёС… СЃРµРєСѓРЅРґ. Р•СЃР»Рё С‚РѕРІР°СЂ РЅРµ Р±С‹Р» РІС‹РґР°РЅ, РїРѕР¶Р°Р»СѓР№СЃС‚Р°, РѕР±СЂР°С‚РёС‚РµСЃСЊ Рє РІР»Р°РґРµР»СЊС†Сѓ РјР°РіР°Р·РёРЅР° РёР»Рё СЃРµСЂРІРµСЂР°."
                },
                pending: {
                    title: "РћР¶РёРґР°РЅРёРµ РѕРїР»Р°С‚С‹",
                    content: "РћРїР»Р°С‚Р° РµС‰Рµ РЅРµ СЃРѕРІРµСЂС€РµРЅР°. Р—Р°РІРµСЂС€РёС‚Рµ РїСЂРѕС†РµСЃСЃ РѕРїР»Р°С‚С‹, С‡С‚РѕР±С‹ РїРѕР»СѓС‡РёС‚СЊ С‚РѕРІР°СЂС‹ РЅР° СЃРµСЂРІРµСЂРµ."
                },
                fail: {
                    title: "РћС€РёР±РєР° РѕРїР»Р°С‚С‹",
                    content: "РћРїР»Р°С‚Р° РЅРµ СѓРґР°Р»Р°СЃСЊ. РџРѕРїСЂРѕР±СѓР№С‚Рµ РїРѕРІС‚РѕСЂРёС‚СЊ РѕРїРµСЂР°С†РёСЋ РµС‰Рµ СЂР°Р·."
                }
            },
            e = window.location.hash.slice(1);
        if (a.hasOwnProperty(e)) {
            var s = '                    <div class="page">                        <h2>' + a[e].title + "</h2>                        " + a[e].content + "                    </div>";
            C.show({
                content: s,
                isSmall: !0
            })
        }
        navigator.platform && /iPad|iPhone|iPod/.test(navigator.platform) && $("body").addClass("ios-ruble-fix")
    }

    function v() {
        function t() {
            var t = "https://vk.com/js/api/openapi.js",
                a = 158,
                e = [];
            window.vkAsyncInit = function() {
                e.forEach(function(t) {
                    t()
                })
            }, this.messages = function(s) {
                e.push(function() {
                    window.VK.Widgets.CommunityMessages("vk_community_messages", s, {
                        tooltipButtonText: "Р•СЃС‚СЊ РІРѕРїСЂРѕСЃ?"
                    }), $(".cart-button").css("bottom", "80px")
                }), g(t + "?" + a)
            }, this.group = function(s) {
                e.push(function() {
                    window.VK.Widgets.Group("vk_groups", {
                        mode: 1,
                        width: "auto",
                        no_cover: 1,
                        color1: "ffffff"
                    }, s)
                }), g(t + "?" + a)
            }
        }
        this.snow = function(t) {
            var a = {
                default: function() {
                    for (var t = [], a = 1; a < 20; a++) t.push("flake" + a + ".png");
                    return t.join(",")
                },
                minecraft: function() {
                    return "flake1.png,flake2.png,flake3.png,flake4.png"
                }
            };
            g("libs/snow-3d/snow-3d-vendor.min.js", function() {
                g("libs/snow-3d/snow-3d.min.js", function() {
                    $("body").snow3d({
                        url: "/statics/js/libs/snow-3d/flakes/" + t + "/",
                        images: a[t](),
                        num: 300,
                        closeButton: 0,
                        disableMouse: !0,
                        enableMobile: !0,
                        minScale: 5,
                        maxScale: 20,
                        speed: .1
                    })
                })
            })
        }, this.vk = new t
    }

    function f() {
        function t(t, n) {
            s[t] = {}, n.forEach(function(n) {
                s[t][n] = function(s) {
                    y.progress.start(), s.data = s.data || {}, s.data.v = e;
                    var i = Object.keys(s.data).map(function(t) {
                            return t + "=" + encodeURIComponent(s.data[t])
                        }).join("&"),
                        o = window.XDomainRequest || window.XMLHttpRequest,
                        r = new o;
                    r.open("GET", a + t + "." + n + "?" + i, !0), r.onload = function() {
                        4 == r.readyState && 200 == r.status && (y.progress.finish(), s.callback(JSON.parse(r.responseText)))
                    }, r.send()
                }
            })
        }
        var a = "https://api.trademc.org/",
            e = 3,
            s = this;
        t("shop", ["getOnline", "getLastPurchases", "getItems", "buyItems"]), t("data", ["getPopularItems", "getPage", "getSteamProfile", "getCouponData"]), t("payment", ["getWays", "getPayData", "getPayForm"])
    }

    function m() {
        var t = this;
        t.get = function(t) {
            var a = document.cookie.match(new RegExp("(?:^|; )" + t.replace(/([\.$?*|{}\(\)\[\]\\\/\+^])/g, "\\$1") + "=([^;]*)"));
            return a ? decodeURIComponent(a[1]) : void 0
        }, t.set = function(t, a, e) {
            e = e || {};
            var s = e.expires;
            if ("number" == typeof s && s) {
                var n = new Date;
                n.setTime(n.getTime() + 1e3 * s), s = e.expires = n
            }
            s && s.toUTCString && (e.expires = s.toUTCString()), a = encodeURIComponent(a);
            var i = t + "=" + a;
            for (var o in e) {
                i += "; " + o;
                var r = e[o];
                !0 !== r && (i += "=" + r)
            }
            document.cookie = i
        }, t.remove = function(a) {
            t.set(a, "", {
                expires: -1
            })
        }
    }

    function h() {
        try {
            return document.createEvent("TouchEvent"), !0
        } catch (t) {
            return !1
        }
    }

    function g(t, a) {
        if (t = "http" == t.substring(0, 4) ? t : b + t, -1 != x.indexOf(t)) return void(a && a());
        x.push(t), $.ajax({
            url: t,
            dataType: "script",
            success: a || null,
            cache: !0
        })
    }
    p.bindForm = function(t, a) {
        $(t).off().on("submit", function(t) {
            t = t || window.event, t.preventDefault();
            var e = $(this),
                s = e.find("button"),
                n = e.serialize();
            return n = n ? JSON.parse('{"' + n.replace(/&/g, '","').replace(/=/g, '":"') + '"}', function(t, a) {
                return "" === t ? a : decodeURIComponent(a).trim()
            }) : {}, n = $.extend({}, n, a.appendParams), (!a.callbackBefore || !a.callbackBefore(e, n)) && (!s.hasClass("load") && (s.addClass("load"), void _[a.api][a.action]({
                data: n,
                callback: function(t) {
                    if (t.error) return s.removeClass("load"), void y.message.error(t.error.message);
                    a.callbackAfter(e, t.response)
                }
            })))
        })
    }, p.formatText = function(t) {
        return t = t.replace(/\n/g, "<br />").replace(/\[b\](.*?)\[\/b\]/gi, "<strong>$1</strong>").replace(/\[i\](.*?)\[\/i\]/gi, "<em>$1</em>").replace(/\[u\](.*?)\[\/u\]/gi, "<ins>$1</ins>").replace(/\[url=\s*(\w{1,32}:.*?)\s*\](.*?)\[\/url\]/gi, '<a href="$1" target="_blank" rel="nofollow">$2</a>').replace(/([a-z0-9_-]+\.)*[a-z0-9_-]+@[a-z0-9_-]+(\.[a-z0-9_-]+)*\.[a-z]{2,6}/gi, '<a href="mailto:$&">$&</a>').replace(/skype:([a-z][a-z0-9\.,\-_]{5,31})/gi, '<a href="$&">$1</a>').replace(/teamspeak:(([a-z0-9\.,\-_]+)(:[0-9]{1,5})?)/gi, '<a href="ts3server:$1">$1</a>').replace(/(?:https?:\/\/)?((?:[a-z0-9Р°-СЏС‘-]+\.){1,10}(?:СЂС„|СЂСѓСЃ|[a-z]{2,6})(?![a-z])(?:\/(?:&amp;|[a-z0-9Р°-СЏС‘0-9@\#%*_=+?\/&.-])*)?)(?![^<]*>|[^<>]*<\/a)/gi, '<a href="http://$1" target="_blank" rel="nofollow">$1</a>')
    }, p.salesTimerStarted = !1, p.salesTimer = function() {
        function t() {
            var e = (new Date).getTime() / 1e3 | 0;
            $("[data-timer]").each(function() {
                var t = parseInt($(this).attr("data-timer")) - e;
                t < 0 || $(this).text(a(t))
            }), setTimeout(t, 1e3)
        }

        function a(t) {
            var a = t / 86400 | 0,
                s = t / 3600 % 24,
                n = t / 60 % 60,
                i = t % 60,
                o = e(s) + ":" + e(n) + ":" + e(i);
            return a && (o = a + "Рґ. " + o), o
        }

        function e(t) {
            return t = Math.floor(t), t < 10 ? "0" + t : t
        }
        p.salesTimerStarted || (p.salesTimerStarted = !0, t())
    };
    var y = this,
        b = "statics/js/",
        w = {},
        _ = new f,
        k = new m,
        C = new i;
    new p, y.init = function(i) {
        w = i, y.progress = new d, y.message = new n, y.cover = new a, y.currency = new e, y.items = new s, y.widgets = new v, y.cart = new t, y.monitoring = new r, y.notice = new c, y.page = new l, y.modules = new o, y.sci = new u
    };
    var x = []
}
var shop = new Shop;
