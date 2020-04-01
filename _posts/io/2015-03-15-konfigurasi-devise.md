---
layout: post
title: "Konfigurasi Devise"
shorttitle: "Konfigurasi Devise"
desc: "Konfigurasi devise untuk otentikasi."
category: io
tags: [ruby, rails, devise]
---

# Konfigurasi

Tambah gem

    gem 'devise'

Lalu bundle install biasa, lalu generate

    rails generate devise:install

Lalu generate pada model...

    rails generate devise MODEL

Ex

    rails generate devise User

Ingat model itu tanpa S alias single... selanjutnya konfigurasi routing config/routes.rb tambahin ini kalau belum ada

    devise_for :users

# Penggunaan

{% include ads.html %}

Taruh di controller atau di application controller untuk autentikasi keseluruhan

    before_action :authenticate_user!

Helper-helper

    user_signed_in?
    current_user
    user_session

Kalau modelnya buka User alias Member

    before_action :authenticate_member!
    member_signed_in?
    current_member
    member_session

# Konfiguresi pada model

    devise :database_authenticatable, :registerable, :confirmable, :recoverable, stretches: 20

Selengkapnya /config/initializers/devise.rb

## Strong Parameters

    sign_in (Devise::SessionsController#create)
    sign_up (Devise::RegistrationsController#create
    account_update (Devise::RegistrationsController#update)

Rails 4.x pake strong parameters

    class ApplicationController < ActionController::Base
      before_action :configure_permitted_parameters, if: :devise_controller?

      protected

      def configure_permitted_parameters
        devise_parameter_sanitizer.for(:sign_in) { |u| u.permit(:username, :email) }
      end
    end

# Konfigurasi pada view

    rails generate devise:views

Kasus pada model banyak

    rails generate devise:views users
    rails generate devise:views members

Jadinya di users/sessions/new dan admins/sessions/new dan default pada devise/sessions/new

# Omniouth

    config.omniauth :github, 'APP_ID', 'APP_SECRET', scope: 'user,public_repo'

Pada config/initializers/devise.rb
